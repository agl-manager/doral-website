<template>
  <nav class="sticky top-0 w-full z-20">
    <AppAnimations>
      <section v-if="displayInfo" class="w-full flex justify-center bg-primary">
        <section class="p-4 flex justify-between text-white max-w-6xl w-full">
          <p><strong>Doralty</strong> digital business card now available</p>
          <button aria-label="Close" @click="displayInfo = !displayInfo">
            <strong>X</strong>
          </button>
        </section>
      </section>
    </AppAnimations>
    <section class="bg-white shadow backdrop-blur-[10px] w-full flex justify-center">
      <section class="flex justify-between max-w-6xl w-full py-4 mx-4 items-center relative">
        <aside class="w-44">
          <a aria-label="Home" href="#home"
            ><AppIcons asset="logo_full"
          /></a>
        </aside>
        <ul class="gap-8 text-gray-700 font-semibold hidden md:flex">
          <li><a aria-label="Navigation about us" href="#about_us">About Us</a></li>
          <li><a aria-label="Navigation projects" href="#projects">Projects</a></li>
          <li><a aria-label="Navigation leadership" href="#leadership">Leadership</a></li>
          <li><a aria-label="Navigation contact us" href="#contact_us">Contact</a></li>
        </ul>
        <AppDrawer />
        <aside class="hidden md:flex gap-4">
          <button aria-label="Phone">
            <AppIcons asset="phone_nav" />
          </button>
          <button aria-label="Mail">
            <AppIcons asset="mail_nav" />
          </button>
          <button aria-label="Location">
            <AppIcons asset="location_nav" />
          </button>
        </aside>
      </section>
    </section>
  </nav>
</template>
<script lang="ts" setup>
import { ref } from 'vue'
import AppDrawer from '../Drawer/AppDrawer.vue'
import AppIcons from '../ui/Assets/AppIcons.vue'
import AppAnimations from '../ui/AppAnimations.vue'

const displayInfo = ref(true)
</script>
