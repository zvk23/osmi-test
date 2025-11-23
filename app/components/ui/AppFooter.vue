<template>
  <footer class="footer bg-bg-primary border-t-gray-100 border-t-1">
    <div class="flex flex-col lg:flex-row lg:center gap-[20px] px-[16px] py-[24px] lg:gap-[32px] lg:px-[32px] lg:pt-[24px] lg:pb-[40px]">
      <div class="text-gray-900 lg:text-[15px]">© Annonce 2023</div>
      <ul class="flex center gap-[20px] lg:gap-[32px] flex-col lg:flex-row">
        <!-- <li class="text-gray-500 lg:text-[15px]">Документы</li> -->
        <li>
          <NuxtLink to="about" class="text-gray-500 lg:text-[15px]">О Компании</NuxtLink>
        </li>
      </ul>
    </div>
  </footer>
</template>

<script setup lang="ts"></script>

<style scoped></style>
