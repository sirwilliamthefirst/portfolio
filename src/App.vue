<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import Pond from './components/Pond.vue'
</script>

<template>
  <div class="pond_title"><h1>Poetry Pond</h1></div>
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

@font-face {
  font-family: 'cloudy_font';
  src: url('./assets/cotton-cloud.regular.ttf') format('truetype');
}

@keyframes title_pop {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  70% {
    opacity: 1;
    transform: scale(1.2); /* Overshoot - bigger than final */
  }
  100% {
    opacity: 1;
    transform: scale(1); /* Settle to normal size */
  }
}

@keyframes wavy {
  0% {
    opacity: 1;
    top: 2%;
  }
  50% {
    top: 3%;
  }
  100% {
    top: 2%;
    opacity: 1;
  }
}

.pond_title {
  position: fixed;
  color: white;
  width: 100%;
  text-align: center;
  top: 2%;
  z-index: 1;
  font-family: 'cloudy_font';
  pointer-events: none;
  opacity: 1;
  font-size: 1rem;
  animation: wavy 4s ease-in-out infinite;
}
</style>
