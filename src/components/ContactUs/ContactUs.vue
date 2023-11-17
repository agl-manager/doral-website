<template>
  <main class="flex flex-col items-end justify-end md:justify-center text-gray-700">
    <section class="w-full flex justify-center">
      <section class="grid md:grid-cols-2 z-10 w-full p-4 max-w-6xl md:gap-8">
        <aside class="flex flex-col gap-4 items-start my-16 justify-start">
          <h5 class="text-lg md:text-xl xl:text-2xl font-bold text-center md:text-start">
            Contact Us
          </h5>
          <p class="text-center md:text-start md:text-xl">
            If you have any software related issue or question, feel free to get in touch with us.
            We are always here to help you
          </p>
          <article class="flex gap-4 items-center">
            <aside><AppIcons asset="email" /></aside>
            <section class="flex flex-col">
              <h6 class="text-lg font-semibold">Email</h6>
              <p>support@doralsolutions.com</p>
            </section>
          </article>
          <article class="flex gap-4 items-center">
            <aside><AppIcons asset="phone" /></aside>
            <section class="flex flex-col">
              <h6 class="text-lg font-semibold">Phone</h6>
              <p>TBD</p>
            </section>
          </article>
          <article class="flex gap-4 items-center">
            <aside><AppIcons asset="location" /></aside>
            <section class="flex flex-col">
              <h6 class="text-lg font-semibold">Address</h6>
              <p>TBD</p>
            </section>
          </article>
        </aside>
        <section class="flex w-full items-center justify-center my-16">
          <section class="bg-white rounded-[30px] shadow backdrop-blur-[10px] p-8 w-full">
            <form @submit.prevent="() => {}" class="grid grid-cols-2 gap-4">
              <section class="flex flex-col gap-2">
                <label for="name" class="font-semibold">
                  Name
                  <span class="text-red-700">*</span>
                </label>
                <input
                  required
                  type="text"
                  name=""
                  id="name"
                  class="py-2 px-4 bg-white rounded-[10px] border border-slate-200"
                />
              </section>
              <section class="flex flex-col gap-2">
                <label for="email" class="font-semibold">
                  Email
                  <span class="text-red-700">*</span>
                </label>
                <input
                  required
                  type="email"
                  name=""
                  id="email"
                  class="py-2 px-4 bg-white rounded-[10px] border border-slate-200"
                />
              </section>
              <section class="flex flex-col gap-2 col-span-2">
                <label for="Message" class="font-semibold">
                  Message
                  <span class="text-red-700">*</span>
                </label>
                <textarea
                  required
                  type="text"
                  name=""
                  id="Message"
                  rows="5"
                  class="py-2 px-4 bg-white rounded-[10px] border border-slate-200"
                />
                <section class="col-span-2 flex justify-end pt-4">
                  <button
                    class="bg-primary w-min whitespace-nowrap text-white py-2 px-6 rounded-full font-semibold h-min"
                  >
                    Contact Us
                  </button>
                </section>
              </section>
            </form>
          </section>
        </section>
      </section>
    </section>
  </main>
</template>
<script lang="ts" setup>
import AppIcons from '../ui/Assets/AppIcons.vue'
</script>
