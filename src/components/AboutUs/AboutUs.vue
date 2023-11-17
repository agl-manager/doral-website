<template>
  <main class="flex flex-col bg-white items-end justify-end md:justify-center text-gray-700">
    <section class="w-full flex justify-center">
      <section class="grid md:grid-cols-2 z-10 w-full p-4 max-w-6xl md:gap-8">
        <section class="flex w-full items-center justify-center my-16">
          <i class="w-full">
            <AppIcons asset="about_us" />
          </i>
        </section>
        <aside class="flex flex-col gap-4 items-start my-16 justify-start">
          <h5 class="text-lg md:text-xl xl:text-2xl font-bold text-center md:text-start">
            About Us
          </h5>
          <span class="flex items-center"
            ><i class="h-8">
              <AppIcons asset="eye" />
            </i>
            <h6 class="text-xl font-bold text-center md:text-start">Our Vision</h6></span
          >
          <p class="text-center md:text-start md:text-xl">
            At Doral Solutions, we are passionate about harnessing the power of technology to
            transform businesses and drive innovation. As a software development company, we
            specialize in crafting custom solutions that are tailored to meet the unique needs of
            our clients.
          </p>
          <span class="flex items-center"
            ><i class="h-8">
              <AppIcons asset="mission_check" />
            </i>
            <h6 class="text-xl font-bold text-center md:text-start">Our Vision</h6></span
          >
          <p class="text-center md:text-start md:text-xl">
            Our mission is simple yet profound: to empower businesses with cutting edge software
            solutions that enhance efficiency, elevate customer experiences, and accelerate growth.
            We believe that technology should not be a barrier but a bridge to achieving your
            business objectives.
          </p>
        </aside>
      </section>
    </section>
  </main>
</template>
<script lang="ts" setup>
import AppIcons from '../ui/Assets/AppIcons.vue'
</script>
