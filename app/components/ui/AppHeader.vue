<template>
  <header class="header bg-warning-100">
    <div class="flex center justify-between px-[40px] py-[18px]">
      <div class="header__left flex items-center gap-[37px]">
        <NuxtLink class="text-[28px]/[28px] font-semibold header-logo" to="/">Annoncé</NuxtLink>
        <AppCatalogButton />
      </div>

      <div class="header__right items-center gap-[24px] hidden lg:flex">
        <div class="header__city flex items-center gap-[7px]">
          <AppPinIcon />
          <span class="text-[15px]/[24px]">Ростов-на-Дону</span>
        </div>

        <hr class="w-[1px] h-[32px] bg-gray-300 border-none" />

        <span
          class="text-[15px]/[24px] text-blue-500 cursor-pointer font-medium"
        >
          Разместить объявление
        </span>

        <AppUserActions />
      </div>

      <AppCardIcon class="lg:hidden" />
    </div>
  </header>
</template>

<script setup lang="ts">
import AppPinIcon from "~/components/icons/AppPinIcon.vue";
import AppCardIcon from "~/components/icons/AppCardIcon.vue";
import AppUserActions from '~/components/business/AppUserAction.vue'
import AppCatalogButton from "~/components/business/AppCatalogButton.vue";
</script>

<style scoped>
.header-logo {
   font-family: "Noto Serif", serif;
}
</style>