<template>
  <Transition :name="animation" mode="out-in" appear>
    <slot />
  </Transition>
</template>

<script setup lang="ts">
import type { PropType } from 'vue'

type AnimationsTypes =
  | 'fade'
  | 'slide-fade'
  | 'bounce'
  | 'rotate-y'
  | 'rotate-from-top'
  | 'rotate-y-half'

defineProps({
  animation: {
    type: String as PropType<AnimationsTypes>,
    default: 'fade'
  }
})
</script>
<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s ease;
  scale: 1;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* slide-fade */

.slide-fade-enter-active {
  transition: all 0.25s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.5s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(20px);
  opacity: 0;
}

/* bounce */

.bounce-enter-active {
  animation: bounce-in 0.25s;
}

.bounce-leave-active {
  animation: bounce-in 0.25s reverse;
}

@keyframes bounce-in {
  0% {
    transform: scale(0);
  }

  50% {
    transform: scale(1.25);
  }

  100% {
    transform: scale(1);
  }
}

/* rotate-y */
.rotate-y-leave-active,
.rotate-y-enter-active {
  transition: all 0.25s ease-out;
}

.rotate-y-enter-from,
.rotate-y-leave-to {
  transform: scaleX(-1);
  opacity: 0;
}

/* rotate-y half*/
.rotate-y-half-leave-active,
.rotate-y-half-enter-active {
  transition: all 0.25s ease-out;
}

.rotate-y-half-enter-from,
.rotate-y-half-leave-to {
  transform: scaleX(0);
  opacity: 0;
}

/* rotate-from-top */

.rotate-from-top-enter-active {
  animation: rotate-from-top-in 0.3s;
  transform-origin: top;
}

.rotate-from-top-leave-active {
  animation: rotate-from-top-in 0.3s reverse;
  transform-origin: top;
}

@keyframes rotate-from-top-in {
  0% {
    transform: rotateX(90deg);
    opacity: 0;
  }
  100% {
    transform: rotateX(0);
    opacity: 1;
  }
}
</style>
