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
                v-model="state.subject"
                label="Name"
                required
                :error="submitCount ? errors.subject : ''"
              />
              <BaseInput
                v-model="state.to"
                label="Email"
                type="email"
                required
                :error="submitCount ? errors.to : ''"
              />

              <BaseTextArea
                v-model="state.body"
                class="col-span-2"
                label="Message"
                required
                :error="submitCount ? errors.body : ''"
              />
              <section class="col-span-2 flex justify-between pt-4">
                <vue-recaptcha
                  v-show="true"
                  :sitekey="siteCaptchaKey"
                  size="normal"
                  theme="light"
                  hl="tr"
                  ref="vueRecaptcha1"
                  @verify="recaptchaVerified"
                  @expire="recaptchaExpired"
                  @fail="recaptchaFailed"
                  @error="recaptchaError"
                />
                <button
                  aria-label="Contact Us"
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
import { ref, reactive } from 'vue'
import vueRecaptcha from 'vue3-recaptcha2'

const siteCaptchaKey = import.meta.env.VITE_G_RECAPTCHA_SITE_KEY

const vueRecaptcha1 = ref()

const initialState = {
  to: 'rrubio@doralsolutions.com',
  subject: 'mail test',
  body: 'este es el body del correo',
  accessToken: '8bZ2u$7aFpXvR@3yQ4T!6oL5jN#9iH*0eK1sUgWdM+cY(=-_^%G'
}

const state = reactive({
  ...initialState
})

const { validate, setValues, errors, submitCount, submitForm } = useForm({
  validationSchema: yup.object({
    to: yup.string().email().required().label('Email'),
    subject: yup.string().required().label('Name'),
    body: yup.string().required().min(5).label('Message')
  })
})

// fetch api post
const submit = async (payload: any) => {
  // const formData = new FormData()

  // for (const name in payload) {
  //   formData.append(name, payload[name])
  // }
  const response = await fetch('https://doralty-mail-service-3z4ybe2vfa-uc.a.run.app/api/email', {
    method: 'POST', // *GET, POST, PUT, DELETE, etc.
    mode: 'no-cors', // no-cors, *cors, same-origin
    cache: 'no-cache', // *default, no-cache, reload, force-cache, only-if-cached
    credentials: 'same-origin', // include, *same-origin, omit
    headers: {
      'Content-Type': 'application/json'
      // 'Content-Type': 'application/x-www-form-urlencoded'
    },
    redirect: 'follow', // manual, *follow, error
    referrerPolicy: 'no-referrer', // no-referrer, *no-referrer-when-downgrade, origin, origin-when-cross-origin, same-origin, strict-origin, strict-origin-when-cross-origin, unsafe-url
    body: JSON.stringify(payload)
  })
  return await response.json()
}

const handleSubmit = async () => {
  setValues(state)
  const valid = await validate()
  if (valid.valid) {
    await submit(state)
    Object.assign(state, { ...initialState })
  } else {
    submitForm()
  }
}

const recaptchaVerified = (response: string) => {
  state.accessToken = response
}
const recaptchaExpired = () => {
  vueRecaptcha1.value.reset()
}
const recaptchaFailed = () => {}

const recaptchaError = (reason: string) => {
  console.log(reason)
}
</script>
