<template>
  <div class="input-wrapper">
    <input v-model="newTodo" placeholder="Tulis tugas baru..." @keyup.enter="submit" />
    <button @click="submit">Tambah</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useTodoStore } from '../stores/todoStore'

const newTodo = ref('')
const store = useTodoStore()

const submit = () => {
  if (newTodo.value.trim()) {
    store.addTodo(newTodo.value)
    newTodo.value = ''
  }
}
</script>

<style scoped>
.input-wrapper {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

input {
  flex: 1;
  padding: 10px 14px;
  font-size: 15px;
  border: 1px solid #d1d5db;
  border-radius: 10px;
  outline: none;
  transition: 0.2s ease;
}

input:focus {
  border-color: #4f46e5;
  box-shadow: 0 0 0 2px rgba(79, 70, 229, 0.2);
}

button {
  background-color: #4f46e5;
  color: white;
  padding: 10px 18px;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  font-size: 15px;
  transition: background 0.2s ease;
}

button:hover {
  background-color: #4338ca;
}
</style>
