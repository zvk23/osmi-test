<template>
  <div class="app-company-info flex flex-col items-center mx-auto pb-[33px]">
    <img src="/img/company-logo.png" alt="" class="w-[120px] h-[120px]" />
    <h3 class="text-gray-900 text-[24px]/[28px] text-bold mt-[24px]">
      Наследие
    </h3>

    <div class="flex items-center gap-[4px] mt-[12px]">
      <div class="flex items-center gap-[4px]">
        <AppRatingIcon />
        <span class="text-[15px]/[24px] text-gray-900">Документы проверены</span>
      </div>

      <AppDotDivider />

      <div class="flex items-center gap-[4px]">
        <AppStarIcon />
        <span class="text-[15px]/[24px] text-gray-900">4.7</span>
      </div>

      <AppDotDivider />

      <div>
        <span class="text-[15px]/[24px] text-gray-900">19 отзывов</span>
      </div>
    </div>

    <AppButton size="lg" class="mt-[24px] mb-[32px]">
      Показать номер телефона
    </AppButton>

    <ul class="flex items-center gap-[8px]">
      <NuxtLink v-for="tab in tabs" :key="tab.label" :to="tab.tab" custom v-slot="{ isActive, navigate }">
        <li class="flex items-center gap-[5px] text-[15px]/[24px] font-medium px-[12px] py-[8px] bg-gray-100 rounded-[12px] cursor-pointer border-[1px] transition-opacity duration-0.3 hover:opacity-[0.7]" :class="[isActive ? 'border-gray-900' : 'border-transparent']" @click="navigate">
          <span class="text-gray-900">{{ tab.label }}</span>
          <span v-if="tab.count" class="text-gray-500">{{ tab.count }}</span>
        </li>
      </NuxtLink>
    </ul>
  </div>
</template>

<script setup lang="ts">
import AppRatingIcon from "~/components/icons/AppRatingIcon.vue";
import AppStarIcon from "~/components/icons/AppStarIcon.vue";
import AppDotDivider from "~/components/ui/AppDotDivider.vue";
import AppButton from "~/components/ui/AppButton.vue";

const tabs: Array<{ label: string, tab: string, count?: number }> = [
  {
    label: 'Товары и услуги',
    tab: 'goods'
  },
  {
    label: 'Агенты',
    tab: 'agents',
    count: 5
  },
  {
    label: 'О компании',
    tab: 'about'
  }
]
</script>
