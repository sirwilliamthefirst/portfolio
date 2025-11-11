<script setup lang="ts">
import { poemCollection } from '@/data/poems'
import { toEditorSettings } from 'typescript'
import { computed, onMounted, reactive, ref } from 'vue'

interface Poem {
  id: number
  title: string
  author: string
  html: string
}

const props = defineProps<{ id: number }>()
const poem = computed(() => ({
  id: props.id,
  title: poemCollection[props.id]?.title,
  author: poemCollection[props.id]?.author,
  html: poemCollection[props.id]?.html,
}))
</script>

<template>
  <Teleport defer to="#modals">
    <div class="poemPage">
      <h1>{{ poem.title }}</h1>
      <span v-html="poem.html"></span>
    </div>
  </Teleport>
</template>

<style>
.stanza {
  padding: 4% 4%;
}
.poemPage {
  background-color: #faf4ed;
  position: fixed;
  z-index: 3;
  width: 100%;
  border: 1cap;
  padding: 3% 10% 3% 10%;
}
.poemPage > * {
  margin: auto;
  text-align: center;
  width: 100%;
  margin: clamp(10px, 3vw, 20px) 0;
  font-size: 1.2rem;
}
.poemPage > h1 {
  margin: auto;
  text-align: center;
  width: 100%;
  margin: clamp(10px, 3vw, 20px) 0;
  font-size: 2rem;
}
</style>
