<template>
  <section class="flex flex-col gap-2">
    <label :for="id" class="font-semibold">
      {{ label }}
      <span v-if="required" class="text-red-700">*</span>
    </label>
    <textarea
      :required="required"
      :name="id"
      :id="id"
      rows="5"
      class="py-2 px-4 bg-white rounded-[10px] border border-slate-200"
      :value="modelValue"
      @input="$emit('update:modelValue', ($event.target as HTMLInputElement).value)"
    />
    <label v-if="error" :for="id" class="-mt-2 text-xs font-semibold text-red-500">{{
      error
    }}</label>
  </section>
</template>
<script lang="ts" setup>
defineEmits(['update:modelValue'])
defineProps({
  modelValue: { type: String, default: '' },
  label: { type: String, default: '' },
  error: { type: String, default: '' },
  required: { type: Boolean, default: false },
  id: { type: String, default: () => `input-${Math.floor(Math.random() * 100000)}` }
})
</script>
