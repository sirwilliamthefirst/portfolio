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

<style scoped>
.pond_container {
  width: 50vw;
  height: 50vh;
}
</style>
