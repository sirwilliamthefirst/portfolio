<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import Pond from './components/Pond.vue'
</script>

<template>
  <div class="pond_container">
    <Pond></Pond>
  </div>
</template>

<style>
.pond_container {
  width: 100vw;
  height: 100vh;
  margin: 0 auto; /* centers horizontally */
  overflow: hidden;
}
</style>
