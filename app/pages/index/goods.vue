<template>
  <div class="py-[32px]">
    <ClientOnly>
      <div class="flex justify-center mb-[24px] px-[12px] md:p-0">
        <AppSelect
          v-model="selected"
          :options="categories"
          class="w-full max-w-full md:max-w-[300px]"
        />
      </div>
    </ClientOnly>

    <div class="grid grid-cols-1 md:grid-cols-1 lg:grid-cols-4 gap-[8px]">
      <AppGoodCard v-for="good in goods" :good="good" />
    </div>
  </div>
</template>

<script setup lang="ts">
import type { IGood } from "~/types/good.type";
import AppGoodCard from "~/components/business/AppGoodCard.vue";
import AppSelect from "~/components/ui/AppSelect.vue";

const selected = ref("all");

const categories = [
  {
    label: "Категория 1",
    items: [
      { label: "Гробы", value: "grob", count: 5 },
      { label: "Урны", value: "urn", count: 12 },
    ],
  },
  {
    label: "Категория 2",
    items: [
      { label: "Тапки", value: "tapki", count: 2 },
      { label: "Покрывало", value: "pokrivalo", count: 1 },
    ],
  },
];

const goods: IGood[] = [
  {
    name: "Clavia Nord Grand сценическое цифровое пианино",
    price: 450500,
    img: "/img/goods/piano.jpg",
    isHidden: false,
    viewsCount: 750,
    dayCount: 2,
    isPromoted: true,
  },
  {
    name: "Hyundai Sonata 2.0 AT, 2023, 30 км",
    price: 3285000,
    img: "/img/goods/car.jpg",
    isHidden: false,
    viewsCount: 255,
    dayCount: 4,
    isPromoted: false,
  },
  {
    name: "2-х. квартира, 48 м², 1/5 эт.",
    price: 4800000,
    img: "/img/goods/flat.jpg",
    isHidden: false,
    viewsCount: 255,
    dayCount: 2,
    isPromoted: false,
  },
  {
    name: "Старые барабаны",
    price: 7500,
    img: "/img/goods/drums.jpg",
    isHidden: false,
    viewsCount: 255,
    dayCount: 2,
    isPromoted: false,
  },
  {
    name: "DMX сплиттер RJ45 to 4x XLR Stativille",
    price: 7500,
    img: "/img/goods/splitter.jpg",
    isHidden: false,
    viewsCount: 255,
    dayCount: 2,
    isPromoted: false,
  },
  {
    name: "Мотоцикл honda",
    price: 27500,
    img: "/img/goods/honda.jpg",
    isHidden: false,
    viewsCount: 255,
    dayCount: 2,
    isPromoted: false,
  },
  {
    name: "Иж юпитер 5",
    price: 17900,
    img: "/img/goods/ij.jpg",
    isHidden: false,
    viewsCount: 255,
    dayCount: 2,
    isPromoted: false,
  },
  {
    name: "Пылесос кёрхер с водяным мешком для сбора пыли",
    price: 7500,
    img: "/img/goods/cleaner.jpg",
    isHidden: true,
    viewsCount: 255,
    dayCount: 2,
    isPromoted: false,
  },
];
</script>
