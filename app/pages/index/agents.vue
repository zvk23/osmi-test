<template>
  <hr class="border-gray-300" />
  <div class="max-w-[560px] mx-auto py-[33px]">
    <ul class="flex flex-col gap-[12px]">
      <li v-for="(agent, i) in agentsList" :key="i">
        <div class="p-[20px] bg-bg-primary lg:rounded-[20px]">
          <div class="flex gap-[20px]">
            <img
              src="/img/ava.png"
              class="w-[140px] h-[140px] rounded-[20px]"
            />

            <div class="flex flex-col">
              <span class="text-[24px]/[28px] font-bold">{{ agent.name }}</span>

              <div class="flex items-center gap-[4px] mt-[4px]">
                <template v-if="agent.advantages.verifyed">
                  <div class="flex items-center gap-[4px]" >
                    <AppRatingIcon />
                    <span class="text-[15px]/[24px] text-gray-900">Документы проверены</span>
                  </div>
  
                  <AppDotDivider />
                </template>

                <template v-if="agent.advantages.rating">
                  <div class="flex items-center gap-[4px]">
                    <AppStarIcon />
                    <span class="text-[15px]/[24px] text-gray-900">{{ agent.advantages.rating }}</span>
                  </div>
                  <AppDotDivider />
                </template>

                <div>
                  <span class="text-[15px]/[24px] text-gray-900">
                    {{ agent.advantages.reviewsCount ? `${agent.advantages.reviewsCount} отзывов` : 'Нет отзывов' }}
                  </span>
                </div>
              </div>

              <div class="line-clamp-3 text-ellipsis overflow-hidden mt-[12px]">
                {{ agent.text }}
              </div>
            </div>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import AppRatingIcon from "~/components/icons/AppRatingIcon.vue";
import AppStarIcon from "~/components/icons/AppStarIcon.vue";
import AppDotDivider from "~/components/ui/AppDotDivider.vue";

const agentsList = [
  {
    name: "Дмитрий Хитрый",
    advantages: {
      verifyed: true,
      rating: 4.3,
      reviewsCount: 19,
    },
    text: "Помог справиться с потерей и организовать похороны для 126 семей ну и еще чуть описания, чтобы дойти до конца строки и текст будет отсекаться",
  },

  {
    name: "Аполлинарий Землеперекопский",
    advantages: {
      verifyed: true,
      rating: null,
      reviewsCount: null,
    },
    text: "Помог справиться с потерей и организовать похороны для 126 семей.",
  },

  {
    name: "Фёдор Сумкин",
    advantages: {
      verifyed: true,
      rating: 4.3,
      reviewsCount: 19,
    },
    text: "Помог справиться с потерей и организовать похороны для 126 семей ну и еще чуть описания, чтобы дойти до конца строки и текст будет отсекаться",
  },

  {
    name: "Василий Копушин",
    advantages: {
      verifyed: true,
      rating: 4.3,
      reviewsCount: 19,
    },
    text: "Помог справиться с потерей и организовать похороны для 126 семей ну и еще чуть описания, чтобы дойти до конца строки и текст будет отсекаться",
  },

  {
    name: "Феофан Кусмякин",
    advantages: {
      verifyed: true,
      rating: 4.3,
      reviewsCount: 19,
    },
    text: "Помог справиться с потерей и организовать похороны для 126 семей ну и еще чуть описания, чтобы дойти до конца строки и текст будет отсекаться",
  },

  {
    name: "Василиса Землеперекопская",
    advantages: {
      verifyed: true,
      rating: 4.3,
      reviewsCount: 19,
    },
    text: "Помог справиться с потерей и организовать похороны для 126 семей ну и еще чуть описания, чтобы дойти до конца строки и текст будет отсекаться",
  },
];
</script>
