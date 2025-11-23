<script setup lang="ts">
import AppFooter from '@/components/ui/AppFooter.vue';
</script>

<template>
  <div class="layout h-[100vh] flex flex-col">
    <header class="layout__header header bg-warning-100">
      <div class="flex center px-[40px] py-[18px]">
        <div class="header__left flex center gap-[37px]">
          <div class="header__logo">
            <NuxtLink to="/">Annoncé</NuxtLink>
          </div>
          <button>Все категории</button>
        </div>

        <div class="header__right"></div>
      </div>
    </header>

    <div class="layout__content grow-1">
      <slot />
    </div>

    <AppFooter class="layout__footer" />
  </div>
</template>

<style scoped></style>
