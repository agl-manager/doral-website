<template>
  <section class="w-full flex justify-center">
    <span class="py-24 w-full justify-start max-w-6xl overflow-hidden flex">
      <image
        v-for="image in solutions"
        :key="image.value"
        class="shrink-0 w-[250px] flex justify-center"
        :style="{ marginLeft: `${image.marginLeft}px` }"
      >
        <img
          :src="getAsset('images/technologies/' + image.value + '.png')"
          :alt="image.value"
          class="h-24 w-auto"
        />
      </image>
    </span>
  </section>
</template>
<script lang="ts" setup>
import { getAsset } from '@/utils/getAssets'
import { onMounted, ref } from 'vue'

const solutions = ref([
  { value: 'Angular', marginLeft: 0 },
  { value: 'firebase', marginLeft: 0 },
  { value: 'firestore', marginLeft: 0 },
  { value: 'google_big_query', marginLeft: 0 },
  { value: 'google_cloud_platform', marginLeft: 0 },
  { value: 'Jenkins_logo_with_title', marginLeft: 0 },
  { value: 'NET_Core_Logo', marginLeft: 0 },
  { value: 'nodejs-icon-logo', marginLeft: 0 }
])

const animateImage = (image: Record<string, any>) => {
  return new Promise((resolve) => {
    let intervalId = setInterval(() => {
      if (image.marginLeft > -250) {
        image.marginLeft -= 1
      } else {
        clearInterval(intervalId)

        image.marginLeft = 0

        resolve('')
      }
    }, 10) // approximates the 2000ms animation time
  })
}

onMounted(async () => {
  animateImage(solutions.value[0])
  setInterval(() => {
    solutions.value.push(solutions.value.shift() as any)
    animateImage(solutions.value[0])
  }, 2500)
})
</script>
