<template>
  <div class="relative" ref="target">
    <!-- Кнопка -->
    <button
      @click="open = !open"
      class="w-full border border-gray-200 rounded-md p-[16px] flex items-center justify-between text-gray-900 bg-gray-50 cursor pointer"
    >
      <span>{{ currentLabel }}</span>

      <svg
        class="w-4 h-4 transition-transform"
        :class="{ 'rotate-180': open }"
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M6.44472 11.565L10.3297 15.45C10.9147 16.035 11.8597 16.035 12.4447 15.45L16.3297 11.565C17.2747 10.62 16.5997 9 15.2647 9H7.49472C6.15972 9 5.49972 10.62 6.44472 11.565Z"
          fill="#6B6B6B"
        />
      </svg>
    </button>

    <transition name="fade">
      <div
        v-if="open"
        class="absolute left-0 top-full w-full bg-white shadow-xl z-50 rounded-b-[12px] overflow-hidden"
      >
        <div class="text-sm text-neutral-900">
          <div
              class="px-[12px] py-[12px] text-[15px]/[24px] font-medium text-gray-500 cursor-pointer flex items-center justify-between hover:bg-gray-50 transition-colors"
              @click="select({ value: 'all' })"
            >
              Все товары и услуги
              <AppCheckIcon v-if="modelValue === 'all'" />
            </div>
          <template v-for="group in options" :key="group.label">
            <div
              class="px-[12px] pt-[24px] pb-[8px] uppercase text-[13px]/[20px] font-medium text-gray-500"
            >
              {{ group.label }}
            </div>

            <!-- Элементы -->
            <button
              v-for="item in group.items"
              :key="item.value"
              @click="select(item.value)"
              class="w-full flex justify-between items-center p-[12px] hover:bg-gray-50 cursor-pointer text-gray-500 text-[15px]/[24px] transition-colors"
            >
              <div class="flex items-center gap-[8px]">
                <span>{{ item.label }}</span>
                <span class="text-neutral-400">{{ item.count }}</span>
              </div>

              <AppCheckIcon v-if="item.value === modelValue" />
            </button>
          </template>
        </div>
      </div>
    </transition>
  </div>
</template>

<script setup lang="ts">
import AppCheckIcon from "~/components/icons/AppCheckIcon.vue";

const props = defineProps<{
  modelValue: string;
  options: Array<{ label: string; items: Array<any> }>;
}>();

const emit = defineEmits(["update:modelValue"]);

const open = ref(false);
const target = ref(null);

const currentLabel = computed(() => {
  const found = props.options
    .flatMap((g) => g.items)
    .find((item) => item.value === props.modelValue);

  return found ? found.label : "Все товары и услуги";
});

const select = (value) => {
  emit("update:modelValue", value);
  open.value = false;
};
</script>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: 0.15s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-4px);
}
</style>
