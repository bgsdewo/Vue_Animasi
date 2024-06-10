<script setup>
import { ref } from 'vue';

const tasks = ref(['Learn HTML','Learn CSS','Learn JavaScript'])
const newTask = ref('')

function addTask () {
  if(newTask.value) {
    tasks.value.unshift(newTask.value)
    newTask.value =''
  }
}

function removeTask(task) {
  tasks.value = tasks.value.filter((t) => t !== task)
}
</script>

<template>
  <main>
    <div class="container">
      <input type="text" v-model="newTask" @keyup.enter="addTask()" autofocus />
      <transition-group name="list">
        <div class="card-list" v-for="(task,index) in tasks" :key="index" @click="removeTask(task)">{{ task }}</div>
        </transition-group>
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

.list-enter-from{
opacity: 0;
transform: scale(0.6);
}

.list-enter-to{
opacity: 1;
transform: scale(1);
}

.list-enter-active{
transition: all 0.5s ease;
}
</style>