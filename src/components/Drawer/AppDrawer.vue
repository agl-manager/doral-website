<template>
  <aside class="w-12 block md:hidden">
    <button type="button" @click="openModal"><AppIcons asset="h_menu" /></button>
  </aside>
  <TransitionRoot appear :show="isOpen" as="template">
    <Dialog as="div" @close="closeModal" class="relative z-50">
      <TransitionChild
        as="template"
        enter="duration-300 ease-out"
        enter-from="opacity-0"
        enter-to="opacity-100"
        leave="duration-200 ease-in"
        leave-from="opacity-100"
        leave-to="opacity-0"
      >
        <div class="fixed inset-0 bg-black/50" />
      </TransitionChild>

      <div class="fixed inset-0 overflow-y-auto">
        <div class="flex min-h-full items-center justify-end text-center">
          <TransitionChild
            as="template"
            enter="duration-300 ease-out"
            enter-from="opacity-0 scale-95"
            enter-to="opacity-100 scale-100"
            leave="duration-200 ease-in"
            leave-from="opacity-100 scale-100"
            leave-to="opacity-0 scale-95"
          >
            <DialogPanel
              class="absolute w-full max-w-md transform overflow-hidden rounded-l-2xl bg-white p-6 text-left align-middle shadow-xl transition-all h-screen z-50"
            >
              <ul class="text-gray-700 font-semibold divide-y flex flex-col">
                <li class="pb-4 flex justify-center">
                  <a @click="closeModal" href="#home">
                    <div class="w-44">
                      <AppIcons asset="logo_full" />
                    </div>
                  </a>
                </li>
                <li class="p-4"><a @click="closeModal" href="#about_us">About Us</a></li>
                <li class="p-4"><a @click="closeModal" href="#projects">Projects</a></li>
                <li class="p-4"><a @click="closeModal" href="#leadership">Leadership</a></li>
                <li class="p-4"><a @click="closeModal" href="#contact_us">Contact</a></li>
              </ul>
            </DialogPanel>
          </TransitionChild>
        </div>
      </div>
    </Dialog>
  </TransitionRoot>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { TransitionRoot, TransitionChild, Dialog, DialogPanel } from '@headlessui/vue'
import AppIcons from '../ui/Assets/AppIcons.vue'

const isOpen = ref(false)

function closeModal() {
  isOpen.value = false
}
function openModal() {
  isOpen.value = true
}
</script>
