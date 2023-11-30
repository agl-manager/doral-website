<template>
  <main
    class="flex flex-col bg-gradient-to-r from-primary to-secondary items-end justify-end md:justify-center relative"
  >
    <aside
      class="bg-gradient-to-r from-secondary to-secondary/25 h-1/3 sm:1/2 md:h-5/6 max-w-xs md:max-w-sm lg:max-w-md xl:max-w-2xl 2xl:max-w-3xl w-full rounded-3xl z-0 absolute right-0 my-16"
    ></aside>
    <section class="w-full flex justify-center">
      <section class="grid md:grid-cols-2 z-10 w-full p-4 max-w-6xl md:gap-8">
        <aside
          class="flex flex-col gap-8 text-white items-center md:items-start my-16 justify-center"
        >
          <h1 class="text-4xl md:text-3xl xl:text-6xl font-bold text-center md:text-start">
            Professional Software <br />
            Development Services
          </h1>
          <p class="text-center md:text-start md:text-xl">Software engineering and beyond</p>
          <a
            href="https://forms.gle/br98A11nJEKwgMg1A"
            target="_blank"
            class="bg-white w-min whitespace-nowrap text-primary font-semibold py-2 px-6 rounded-full"
          >
            Start Project
          </a>
        </aside>
        <section class="flex w-full items-center justify-center my-16">
          <AppIcons asset="graphics" />
        </section>
      </section>
    </section>
  </main>
</template>
<script lang="ts" setup>
import AppIcons from '../ui/Assets/AppIcons.vue'
</script>
