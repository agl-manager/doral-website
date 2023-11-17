<template>
  <component :is="icon" :key="icon" class="h-full w-full" />
</template>
<script setup lang="ts">
import { computed } from 'vue'
import { getIcon } from '@/utils/getAssets'

const props = defineProps({
  asset: { type: String, required: true }
})

const icon = computed(() => getIcon(props.asset))
</script>
