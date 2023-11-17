<template>
  <section class="w-full bg-white py-12 flex justify-center">
    <section class="max-w-6xl w-full relative mx-12">
      <section class="flex justify-center">
        <div
          class="h-full w-full md:w-2/3 bg-blue-50 mt-16 rounded-t-[5rem] p-12 text-2xl font-bold mx-4 md:mx-0 text-center"
        >
          Projects
          <p class="text-base font-thin">Transforming Businesses One Byte at a Time</p>
        </div>
      </section>
      <section class="w-full p-12 border rounded-3xl">
        <main class="flex w-full justify-between items-center">
          <button class="absolute -left-[3rem]" @click="handlePrev">
            <svg
              width="96"
              height="96"
              viewBox="0 0 96 96"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <circle cx="48" cy="48" r="48" fill="white" />
              <path
                d="M48 72C61.2547 72 72 61.2547 72 48C72 34.7452 61.2547 24 48 24C34.7452 24 24 34.7452 24 48C24 61.2547 34.7452 72 48 72Z"
                stroke="#292D32"
                stroke-width="3"
                stroke-miterlimit="10"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
              <path
                d="M51.0232 56.4719L42.5752 47.9999L51.0232 39.5278"
                stroke="#2787F3"
                stroke-width="3"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </button>
          <section class="grow flex justify-center">
            <AppAnimations animation="rotate-y">
              <ProjectCard :text="items[selected].text" :key="selected" />
            </AppAnimations>
          </section>
          <button class="absolute -right-[3rem]" @click="handleNext">
            <svg
              width="96"
              height="96"
              viewBox="0 0 96 96"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <circle cx="48" cy="48" r="48" fill="white" />
              <path
                d="M48 72C61.2547 72 72 61.2547 72 48C72 34.7452 61.2547 24 48 24C34.7452 24 24 34.7452 24 48C24 61.2547 34.7452 72 48 72Z"
                stroke="#292D32"
                stroke-width="3"
                stroke-miterlimit="10"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
              <path
                d="M44.9766 56.4719L53.4246 47.9999L44.9766 39.5278"
                stroke="#2787F3"
                stroke-width="3"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </button>
        </main>
      </section>
      <section class="flex justify-center">
        <div
          class="h-full w-full md:w-2/3 bg-blue-50 rounded-b-[5rem] p-6 font-bold mx-4 md:mx-0 text-center"
        />
      </section>
    </section>
  </section>
</template>
<script lang="ts" setup>
import { ref } from 'vue'
import ProjectCard from './ProjectCard.vue'
import AppAnimations from '../ui/AppAnimations.vue'
const selected = ref(0)
const items = [
  {
    text: 'Doralty is the perfect solution to help you seize opportunities and make better connections. Exchange contacts easily with our <strong>Digital Business Card</strong>.'
  },
  {
    text: 'Doralty is the perfect solution to help you seize opportunities and make better connections. Exchange contacts easily with our <strong>Digital Business Card</strong>.'
  }
]
const handleNext = () => {
  if (selected.value < items.length - 1) {
    selected.value++
  } else {
    selected.value = 0
  }
}
const handlePrev = () => {
  if (selected.value > 0) {
    selected.value--
  } else {
    selected.value = items.length - 1
  }
}
</script>
