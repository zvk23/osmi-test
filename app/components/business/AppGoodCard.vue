<template>
  <div
    class="bg-white overflow-hidden p-[8px] flex flex-col"
  >
    <div class="w-full">
      <div class="relative">
        <img :src="good.img" alt="" class="rounded-[20px] w-full">

        <div class="absolute top-[8px] left-[8px] flex items-center gap-[4px]">
          <div class="rounded-[12px] text-white text-[13px]/[20px] bg-gray-60/60 px-[8px] py-[4px] flex items-center gap-[8px]">
            <AppEyeIcon class="w-[24px] h-[24px]" /> {{ good.viewsCount }}
          </div>

          <div class="rounded-[12px] text-white text-[13px]/[20px] bg-gray-60/60 px-[8px] py-[4px] flex items-center gap-[8px]">
            <AppCelendarIcon class="w-[24px] h-[24px]" /> {{ good.dayCount }}
          </div>
        </div>
      </div>

      <div class="text-[17px][20px] font-medium mt-[16px] mb-[9px] flex flex-col gap-[12px]">
        <span class="">{{ currencyFormatter.format(good.price)}}</span>
        <span>{{ good.name }}</span>
      </div>

      <hr class="border-gray-100 my-[12px]">

      <div class="flex">
        <template v-if="good.isHidden">
          <span class="text-center text-[15px]/[40px] mx-auto text-negative-500">Объявление скрыто</span>
        </template>

        <template v-else-if="good.isPromoted">
          <span class="text-center text-[15px]/[40px] mx-auto text-blue-500">Объявление продвигается</span>
        </template>

        <template v-else>
          <div class="flex items-center justify-between w-full">
            <span class="text-[13px]/[18px] text-gray-500">Увеличьте количество просмотров</span>
            <AppButton size="sm">Продвигать</AppButton>
          </div>
        </template>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import type { IGood } from "~/types/good.type";
import AppEyeIcon from "~/components/icons/AppEyeIcon.vue";
import AppCelendarIcon from "~/components/icons/AppCelendarIcon.vue";
import AppButton from "~/components/ui/AppButton.vue";

defineProps<{ good: IGood }>();

const currencyFormatter = new Intl.NumberFormat("ru-RU", { style: "currency", currency: "RUB", minimumFractionDigits: 0 })
</script>
