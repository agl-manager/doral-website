<template>
  <section class="w-full bg-white py-12 flex justify-center">
    <section class="max-w-6xl w-full relative mx-12">
      <section class="flex justify-center">
        <div
          class="h-full md:h-2/3 w-full md:w-2/3 bg-blue-50 mt-16 rounded-t-[5rem] p-12 text-2xl font-bold md:mx-0 text-center"
        >
          Leadership
          <p class="text-base font-thin">Digital Transformation is Your Path to Success</p>
        </div>
      </section>
      <section class="flex justify-center items-center relative px-4 pb-8">
        <div
          class="w-full md:w-2/3 bg-blue-50 rounded-b-[5rem] p-6 font-bold mx-4 md:mx-0 text-center absolute top-0 z-0 h-full"
        />
        <section class="grid lg:grid-cols-6 w-full relative gap-4">
          <LeaderCard
            v-for="(leader, i) in leaders"
            :key="leader.job_name"
            :job_name="leader.job_name"
            :image="leader.image"
            :name="leader.name"
            :class="[
              (i + 1) % 3
                ? i + 1 < 3
                  ? 'col-span-6 md:col-span-3 lg:col-span-2 justify-center'
                  : (i + 1) % 2
                    ? 'col-span-6 md:col-span-3 justify-center  lg:justify-start'
                    : 'col-span-6 md:col-span-3 justify-center  lg:justify-end'
                : 'col-span-6 lg:col-span-2 justify-center'
            ]"
          />
        </section>
      </section>
    </section>
  </section>
</template>
<script lang="ts" setup>
import LeaderCard from './LeaderCard.vue'

const leaders = [
  {
    image: 'rene',
    name: 'Rene Rubio',
    job_name: 'CEO and CoFounder'
  },
  {
    image: 'maria',
    name: 'Maria Teresa Rosales',
    job_name: 'CPO and CoFounder'
  },
  {
    image: 'osmin',
    name: 'Osmin Perez',
    job_name: 'CTO and CoFounder'
  },
  {
    image: 'yusmari',
    name: 'Yusmari Companioni',
    job_name: 'CQO and CoFounder'
  },
  {
    image: 'julio',
    name: 'Julio Garcia',
    job_name: 'CSO and CoFounder'
  }
]
</script>
