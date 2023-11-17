<template>
  <section>
    <section class="flex justify-center">
      <div
        class="h-full w-full md:w-2/3 lg:w-1/3 bg-white mt-16 rounded-t-[5rem] p-12 text-2xl font-bold mx-4 md:mx-0 text-center"
      >
        Why Choose Us
      </div>
    </section>
    <section class="flex relative justify-center px-4 mx-4 md:mx-0">
      <div class="absolute z-0 top-0 h-full w-full md:w-2/3 lg:w-1/3 bg-white" />
      <div class="absolute z-0 bottom-0 w-full bg-white h-1/4" />
      <section class="w-full grid md:grid-cols-2 lg:grid-cols-3 max-w-6xl z-10 gap-4">
        <ChoseCard
          icon="user"
          title="Client Focus"
          content="We take pride in building strong relationships with our clients. Your success is
our success, and we work collaboratively to ensure our solutions align with your goals."
        />
        <ChoseCard
          icon="gap"
          title="Expertise"
          content="Wide team of engineers with a deep understanding of the latest technologies and trends. We stay at the
forefront of the digital landscape to deliver solutions that keep you ahead of the competition."
        />
        <ChoseCard
          icon="bulb"
          title="Innovation"
          content="We thrive on innovation. Our team is constantly exploring new ideas and approaches to
solve complex challenges and provide you with the best possible solutions."
        />
        <ChoseCard
          icon="trophy"
          title="Quality Assurance"
          content="Quality is non-negotiable for us. We follow industry best practices and rigorous
quality assurance processes to deliver software that meets the highest standards."
        />
        <ChoseCard
          icon="settings"
          title="Tailored Solutions"
          content="We understand that one size does not fit all. Our solutions are customized to fit your
specific requirements, ensuring they seamlessly integrate into your business operations."
        />
        <ChoseCard title="Assured Success " bg="bg-cyan-100" text="text-gray-700">
          <button
            class="bg-primary w-min whitespace-nowrap text-white py-2 px-6 rounded-full font-semibold"
          >
            Contact Us
          </button>
        </ChoseCard>
      </section>
    </section>
  </section>
</template>
<script lang="ts" setup>
import ChoseCard from './ChoseCard.vue'
</script>
