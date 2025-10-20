<script setup lang="ts">
import { ref } from 'vue'
import Ripple from './Ripple.vue'
const ripples = ref<{ x: number; y: number }[]>([])
function createRipple(event: MouseEvent) {
  ripples.value.push({ x: event.clientX, y: event.clientY })
  console.log(event.clientX, event.clientY)
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
  /*background: linear-gradient(to bottom, lightblue, rgb(72, 72, 124));*/
  background: radial-gradient(circle, lightblue, rgb(72, 72, 124));
  width: 100%;
  height: 100%;
}
</style>
