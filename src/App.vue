<script setup lang="ts">
import Pond from './components/Pond.vue'
</script>

<template>
  <div class="pond_container">
    <Pond></Pond>
  </div>
</template>

<style>
.pond_container {
  position: fixed;
  width: 100vw;
  height: 100vh;
  margin: 0 auto; /* centers horizontally */
  overflow: auto;
  z-index: 2;
}
</style>
