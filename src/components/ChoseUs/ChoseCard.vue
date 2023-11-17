<template>
  <section
    class="p-6 rounded-xl flex flex-col gap-4 items-center justify-center"
    :class="[bg, text]"
  >
    <i class="w-10">
      <AppIcons v-if="icon" :asset="icon" />
    </i>
    <h4 v-if="title" class="font-bold text-xl">
      {{ title }}
    </h4>
    <slot>
      <p v-if="content" class="text-center">{{ content }}</p>
    </slot>
  </section>
</template>
<script lang="ts" setup>
import AppIcons from '../ui/Assets/AppIcons.vue'

defineProps({
  icon: { type: String },
  content: { type: String },
  bg: { type: String, default: 'bg-primary' },
  text: { type: String, default: 'text-white' },
  title: { type: String }
})
</script>
