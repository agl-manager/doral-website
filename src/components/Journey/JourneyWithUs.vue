<template>
  <div class="flex flex-col items-center bg-primary">
    <main
      class="flex flex-col bg-white items-end justify-end md:justify-center text-gray-700 relative w-full"
    >
      <section class="w-full h-1/2 bg-primary absolute bottom-0 z-0"></section>
      <section class="w-full flex justify-center">
        <section class="z-10 w-full p-4 max-w-6xl md:gap-8">
          <i class="w-full">
            <img :src="getAsset('images/journey.png')" class="w-full h-auto" />
          </i>
        </section>
      </section>
    </main>
    <section class="max-w-6xl w-full flex flex-col gap-4 text-white items-center pb-12">
      <h2 class="text-3xl text-center font-semibold">Join us on the Digital Journey</h2>
      <p class="text-center text-lg">
        Join us on a journey of innovation and transformation. Whether you are a startup looking to
        disrupt the market or an established enterprise seeking to stay ahead, Doral Solutions is
        here to help you achieve your digital goals.
      </p>
    </section>
    <section class="flex flex-col gap-4 text-primary items-center relative w-full">
      <section class="w-full h-1/2 bg-white absolute bottom-0 z-0"></section>
      <article
        class="bg-white bg-opacity-95 rounded-[50px] shadow backdrop-blur-[10px] p-8 px-12 flex gap-12 items-center max-w-6xl w-full justify-center flex-col md:flex-row"
      >
        <p class="text-3xl max-w-lg">
          Ready to embark on your digital journey? Let’s make it happen, together.
        </p>
        <a
          href="#contact_us"
          class="bg-primary w-min whitespace-nowrap text-white py-2 px-6 rounded-full font-semibold h-min"
        >
          Contact Us
        </a>
      </article>
    </section>
  </div>
</template>
<script lang="ts" setup>
import { getAsset } from '@/utils/getAssets'
</script>
