<template>
  <section class="w-full flex justify-center">
    <section class="py-24 w-full flex justify-evenly max-w-6xl">
      <image class="w-44">
        <AppIcons asset="logo_mono" />
      </image>
      <image class="w-44 hidden md:block">
        <AppIcons asset="logo_mono" />
      </image>
      <image class="w-44 hidden lg:block">
        <AppIcons asset="logo_mono" />
      </image>
      <image class="w-44 hidden xl:block">
        <AppIcons asset="logo_mono" />
      </image>
      <image class="w-44 hidden xl:block">
        <AppIcons asset="logo_mono" />
      </image>
    </section>
  </section>
</template>
<script lang="ts" setup>
import AppIcons from '../ui/Assets/AppIcons.vue'
</script>
