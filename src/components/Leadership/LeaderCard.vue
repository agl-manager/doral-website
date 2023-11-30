<template>
  <section class="w-full flex">
    <article class="max-w-xs w-full">
      <header class="flex flex-col relative w-full items-center">
        <section
          class="w-full h-1/2 absolute bottom-0 z-0 bg-white rounded-t-[30px] border-t border-x border-slate-200"
        />

        <img
          :src="getAsset(`images/${image}.png`)"
          alt=""
          class="w-32 h-32 object-cover rounded-full z-10"
        />
      </header>
      <section
        class="w-full p-5 gap-2 bg-white rounded-b-[30px] border-b border-x border-slate-200 flex flex-col items-center"
      >
        <h4 class="font-semibold">{{ name }}</h4>
        <p class="font-thin text-xs">{{ job_name }}</p>
      </section>
    </article>
  </section>
</template>
<script lang="ts" setup>
import { getAsset } from '@/utils/getAssets'

defineProps({ image: { type: String }, name: { type: String }, job_name: { type: String } })
</script>
