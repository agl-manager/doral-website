<template>
  <section class="flex flex-col relative">
    <section class="bg-gradient-to-r from-primary to-secondary h-1/2 w-full z-0 absolute top-0" />
    <section class="w-full flex justify-center z-10">
      <section class="max-w-6xl w-full grid md:grid-cols-3 p-8 md:p-4 text-gray-700">
        <aside
          class="bg-gradient-to-b from-blue-100 to-white shadow backdrop-blur-[10px] p-8 rounded-3xl flex flex-col items-center gap-4 hover:scale-95 transition-all duration-200"
        >
          <header class="w-24">
            <img :src="getAsset('images/comunity.png')" alt="" />
          </header>
          <h4 class="font-bold">Consulting and Strategy</h4>
          <p class="mx-4 text-sm text-center">
            Our experts provide strategic guidance to help you make informed decisions and maximize
            the potential of technology
          </p>
        </aside>
        <aside
          class="bg-gradient-to-b from-blue-100 to-white shadow backdrop-blur-[10px] p-8 rounded-3xl flex flex-col items-center scale-115 z-10 gap-4 hover:scale-125 transition-all duration-200"
        >
          <header class="w-24">
            <img :src="getAsset('images/star.png')" alt="" />
          </header>
          <h4 class="font-bold">Custom Development</h4>
          <p class="mx-4 text-sm text-center">
            We design, develop, and deploy custom software solutions that align with your business
            objectives and scale with your growth
          </p>
        </aside>
        <aside
          class="bg-gradient-to-b from-blue-100 to-white shadow backdrop-blur-[10px] p-8 rounded-3xl flex flex-col items-center gap-4 hover:scale-95 transition-all duration-200"
        >
          <header class="w-24">
            <img :src="getAsset('images/chat.png')" alt="" />
          </header>
          <h4 class="font-bold">Support and Maintenance</h4>
          <p class="mx-4 text-sm text-center">
            We offer ongoing support and excellent maintenance services to keep your software
            running and always up to date
          </p>
        </aside>
      </section>
    </section>
  </section>
</template>
<script lang="ts" setup>
import { getAsset } from '@/utils/getAssets'
</script>
