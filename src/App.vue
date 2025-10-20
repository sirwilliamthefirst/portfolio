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
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}
.pond_container {
  min-height: 50vh; /* or however tall you want */
  min-width: 50vw;
}
body,
html {
  margin: 0;
  padding: 0;
  height: 100%;
  background: #111;
  overflow: hidden;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
