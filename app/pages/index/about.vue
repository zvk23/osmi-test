<template>
  <hr class="border-gray-300" />

  <div class="max-w-[560px] mx-auto py-[33px] flex flex-col gap-[12px]">
    <div class="p-[20px]">
      <h3 class="font-bold text-[24px]/[28px] mb-[8px]">О компании</h3>
      <span class="text-[17px]/[28px]"
        >Копкой занимаемся 15 лет. Все началось с хобби и плавно переросло в
        любимую работу. Работаем с профессиональной техникой.
      </span>
    </div>

    <div class="p-[20px] bg-gray-100 rounded-[12px] opacity-[0.3]">
      <div class="flex justify-between">
        <h3 class="font-bold text-[24px]/[28px] mb-[8px]">Режим работы</h3>
        <AppArrowIcon />
      </div>

      <div class="text-[17px]/[28px]">
        Сегодня с 8:00 до 23:00
      </div>
    </div>

    <div class="pr-0 rounded-[12px] flex overflow-hidden">
      <div class="p-[20px]">
        <h3 class="font-bold text-[24px]/[28px] mb-[8px]">Местоположение</h3>
  
        <div class="text-[17px]/[28px] text-blue-500">
          <a href="https://www.google.com/maps?q=47.2441874,39.6777074&z=16" target="_blank">Ростов на Дону, Воронежская ул., 42А корп. 1</a>
        </div>
      </div>

      <img src="/img/map.jpg" alt="" class="h-[132px]">
    </div>
  </div>
</template>

<script setup lang="ts">
import AppArrowIcon from '~/components/icons/AppArrowIcon.vue';
</script>

<style scoped></style>
