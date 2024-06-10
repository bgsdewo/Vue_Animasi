<script setup>
import { ref } from 'vue';


</script>

<template>
  <main>
    <div class="container">
      <input type="text" autofocus/>
      <div class="card-list">Task 1</div>
      <div class="card-list">Task 2</div>
      <div class="card-list">Task 3</div>
    </div>
  </main>
</template>

<style scoped>
.container {
  max-width: 300px;
  margin: 0 auto;

}

.container input {
  width: 100px;
  border-radius: 5px;
  border: 1px solid #ccc;
  padding: 10px;
  margin-bottom: 20px;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
}

.card-list {
  width: 300px;
  border-radius: 5px;
  padding: 5px 10px;
  margin-top: 10px;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  cursor: pointer;
}
</style>