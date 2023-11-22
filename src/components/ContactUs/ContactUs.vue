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
              <p>+1 (954) 840-3224</p>
            </section>
          </article>
          <article class="flex gap-4 items-center">
            <aside><AppIcons asset="location" /></aside>
            <section class="flex flex-col">
              <h6 class="text-lg font-semibold">Address</h6>
              <p>6193 NW 183rd St, Hialeah, FL, 33017 #171672</p>
            </section>
          </article>
        </aside>
        <section class="flex w-full items-center justify-center my-16">
          <section class="bg-white rounded-[30px] shadow backdrop-blur-[10px] p-8 w-full">
            <form @submit.prevent="handleSubmit" class="grid grid-cols-2 gap-4">
              <BaseInput
                v-model="state.name"
                label="Name"
                required
                :error="submitCount ? errors.name : ''"
              />
              <BaseInput
                v-model="state.email"
                label="Email"
                type="email"
                required
                :error="submitCount ? errors.email : ''"
              />

              <BaseTextArea
                v-model="state.message"
                class="col-span-2"
                label="Message"
                required
                :error="submitCount ? errors.message : ''"
              />
              <section class="col-span-2 flex justify-end pt-4">
                <button
                  class="bg-primary w-min whitespace-nowrap text-white py-2 px-6 rounded-full font-semibold h-min"
                >
                  Contact Us
                </button>
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
import * as yup from 'yup'
import { useForm } from 'vee-validate'
import BaseInput from '../ui/inputs/BaseInput.vue'
import BaseTextArea from '../ui/inputs/BaseTextArea.vue'
import { reactive } from 'vue'

const initialState = {
  email: '',
  name: '',
  message: ''
}

const state = reactive({
  ...initialState
})

const { validate, setValues, errors, submitCount, submitForm } = useForm({
  validationSchema: yup.object({
    email: yup.string().email().required().label('Email'),
    name: yup.string().required().label('Name'),
    message: yup.string().required().min(50).label('Message')
  })
})

const handleSubmit = async () => {
  setValues(state)
  const valid = await validate()
  if (valid.valid) {
    //
    Object.assign(state, { ...initialState })
  } else {
    submitForm()
  }
}
</script>
