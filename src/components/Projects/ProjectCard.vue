<template>
  <section class="flex w-3/4 flex-col md:flex-row gap-12">
    <aside class="w-1/3">
      <img :src="getAsset('images/card.png')" alt="" />
    </aside>
    <article class="flex flex-col gap-4 items-start justify-between">
      <header class="h-12">
        <AppIcons asset="logo_full" />
      </header>
      <p class="max-w-sm" v-html="text"></p>
      <button
        class="bg-primary w-min whitespace-nowrap text-white py-2 px-6 rounded-full font-semibold"
      >
        Learn More
      </button>
    </article>
  </section>
</template>
<script lang="ts" setup>
import { getAsset } from '@/utils/getAssets'
import AppIcons from '../ui/Assets/AppIcons.vue'
defineProps({
  text: { type: String }
})
</script>
