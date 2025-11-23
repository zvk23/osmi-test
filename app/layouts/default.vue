<script setup lang="ts">
import AppFooter from '@/components/ui/AppFooter.vue';
import AppHeader from '@/components/ui/AppHeader.vue';
import AppCompanyInfo from '@/components/business/AppCompanyInfo.vue';
</script>

<template>
  <div class="layout h-[100vh] flex flex-col">
    <AppHeader class="layout__header" />
    <AppCompanyInfo />

    <div class="layout__content grow-1">
      <slot />
    </div>

    <AppFooter class="layout__footer" />
  </div>
</template>

<style scoped></style>
