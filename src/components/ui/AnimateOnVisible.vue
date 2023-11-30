<template>
  <div ref="childRef" class="min-h-12 min-w-12">
    <AppAnimations>
      <slot v-if="show" />
    </AppAnimations>
  </div>
</template>
<script lang="ts" setup>
import { ref, onMounted, nextTick, onBeforeUnmount, watch, computed } from 'vue'
import AppAnimations from './AppAnimations.vue'

const childRef = ref<HTMLDivElement>()

const show = ref(true)

// IntersectionObserver setup
const observer = new IntersectionObserver(
  (entries) => {
    entries.forEach((entry) => {
      console.log(entry.isIntersecting)
      if (entry.isIntersecting) {
        show.value = true
      } else {
        show.value = false
      }
    })
  },
  {
    root: null,
    rootMargin: '0px'
    // threshold: Array.from(Array(100).keys()).map((v) => v / 100)
  }
)

const startObserving = async (target = childRef) => {
  await nextTick()
  if (target.value) observer.observe(target.value)
}

const stopObserving = () => observer.disconnect()

onMounted(async () => {
  startObserving()
})

onBeforeUnmount(stopObserving)
</script>
