<template>
  <footer class="flex flex-col w-full">
    <header class="flex py-6 justify-center bg-gradient-to-r from-primary to-secondary">
      <section class="max-w-6xl w-full flex flex-col items-center justify-center gap-6">
        <i class="w-24">
          <a href="#home">
            <AppIcons asset="logo_white" />
          </a>
        </i>
        <ul class="flex gap-8 text-white font-semibold">
          <li><a href="#about_us">About Us</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#leadership">Leadership</a></li>
          <li><a href="#contact_us">Contact</a></li>
        </ul>
      </section>
    </header>
    <footer class="flex py-6 justify-center">
      <section class="max-w-6xl w-full flex flex-col items-center justify-center">
        <p>
          © 2023 Doral Solutions Powered by
          <strong><a href="https://exeditec.com/">EXEDITEC</a></strong>
        </p>
      </section>
    </footer>
  </footer>
</template>
<script lang="ts" setup>
import AppIcons from '../ui/Assets/AppIcons.vue'
</script>
