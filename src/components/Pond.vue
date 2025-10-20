<script setup lang="ts">
import { ref } from 'vue'
import Ripple from './Ripple.vue'
const ripples = ref<{ x: number; y: number }[]>([])
function createRipple(event: MouseEvent) {
  const target = event.currentTarget as HTMLElement
  const rect = target.getBoundingClientRect()
  const x = event.clientX - rect.left
  const y = event.clientY - rect.top
  ripples.value.push({ x, y })
}
</script>

<template>
  <div @click="createRipple" class="pond">
    <template v-for="ripple in ripples">
      <Ripple :style="{ left: ripple.x + 'px', top: ripple.y + 'px' }"></Ripple>
    </template>
  </div>
</template>

<style>
.pond {
  background: radial-gradient(circle, lightblue, rgb(72, 72, 124));
  width: 100%;
  height: 100%;
}
</style>
