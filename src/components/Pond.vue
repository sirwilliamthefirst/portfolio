<script setup lang="ts">
import { ref } from 'vue'
import Ripple from './Ripple.vue'
import Page from './Page.vue'
const ripples = ref<{ x: number; y: number; id: number }[]>([])
const lastClick = ref({ x: 0, y: 0 })
let rippleNextId = 0
function createRipple(event: MouseEvent) {
  console.log('create ripple!')
  const target = event.currentTarget as HTMLElement
  const rect = target.getBoundingClientRect()
  const x = event.clientX - rect.left
  const y = event.clientY - rect.top
  rippleNextId++
  console.log('click pos: ' + x + ', ' + y)
  let id = rippleNextId
  ripples.value.push({ x, y, id })
  lastClick.value = { x, y }
}

function filterRipple(id: number) {
  console.log(ripples.value.length, id)

  ripples.value = ripples.value.filter((x) => x.id != id)
  console.log(ripples.value.length)
}
</script>

<template>
  <div @click="createRipple" class="pond">
    <template v-for="ripple in ripples" :key="ripple.id">
      <Ripple
        @deleteRipple="filterRipple"
        :id="ripple.id"
        :style="{ left: ripple.x + 'px', top: ripple.y + 'px' }"
      ></Ripple>
    </template>
    <Page :lastRipple="lastClick"></Page>
    <Page :lastRipple="lastClick"></Page>
    <Page :lastRipple="lastClick"></Page>
    <Page :lastRipple="lastClick"></Page>
    <Page :lastRipple="lastClick"></Page>
    <Page :lastRipple="lastClick"></Page>
    <Page :lastRipple="lastClick"></Page>
  </div>
</template>

<style>
.pond {
  background: radial-gradient(circle, lightblue, rgb(72, 72, 124));
  width: 100%;
  height: 100%;
  position: relative;
}
</style>
