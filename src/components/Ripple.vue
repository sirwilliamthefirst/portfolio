<script setup lang="ts"></script>

<template>
  <div :="$attrs" class="ripple"></div>
</template>

<style>
@keyframes ripple-ring {
  from {
    transform: scale(1);
    opacity: 0.5;
  }
  to {
    transform: scale(7);
    opacity: 0;
  }
}
.ripple {
  position: absolute;
  width: 20px;
  height: 20px;
  z-index: 1;
  border: 1px solid rgba(255, 255, 255, 0.5);
  background: transparent;
  border-radius: 50%;
  animation: ripple-ring 2s ease-out forwards;
  pointer-events: none;
}
</style>
