<template>
  <button class="bg-blue-500 rounded-[12px] cursor-pointer text-[15px]/[24px] font-medium transition-opacity duration-0.3 hover:opacity-[0.7]" :class="size === 'lg' ? lgButtonClasses : smButtonClasses">
    <span class="text-white">
      <slot />
    </span>
  </button>
</template>

<script setup lang="ts">
const props = defineProps<{ size: "sm" | "lg" }>();

const lgButtonClasses = 'px-[24px] py-[16px]'
const smButtonClasses = 'px-[12px] py-[8px]'

</script>

<style scoped></style>
