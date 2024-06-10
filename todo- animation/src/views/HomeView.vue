<script setup>
import { ref } from 'vue';

const showText = ref(false)
</script>

<template>
  <main>
    <div class="container">
      <transition name="fade">
        <h1 v-if="showText">Hello World</h1>
        <h1 v-else>GoodBye</h1>
      </transition>
      <button @click="showText = !showText">Toggle</button>
    </div>
  </main>
</template>

<style scoped>

.container {
  position: relative;
}

h1 {
  position: absolute;
}

button {
  margin-top: 100px;
}

.fade-enter-from {
  opacity: 0;
}

.fade-enter-to {
  opacity: 1;  
}

.fade-enter-active {
  transition: all 1s ease;
}

.fade-leave-from {
  opacity: 1;  
}

.fade-leave-to {
  opacity: 0;
}

.fade-leave-active {
  transition: all 1s ease;
}
</style>