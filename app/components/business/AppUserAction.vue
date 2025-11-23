<template>
  <div class="user-actions rounded-full p-[4px] pl-[12px] bg-gray-100 flex items-center gap-[11px] cursor-pointer">
    <AppBurgerIcon />
    
    <div>
      <img class="w-[40px] h-[40px] rounded-full" src="/img/ava.png" alt="">
    </div>
  </div>
</template>

<script setup lang="ts">
import AppBurgerIcon from '~/components/icons/AppBurgerIcon.vue'
</script>

<style scoped></style>
