<template>
  <div class="container">
    <div class="todo-card">
      <h1>Daftar Tugas</h1>
      <p class="subtitle">Kelola tugas harianmu dengan mudah dan nyaman</p>
      <TodoInput />
      <TodoList />
      <TodoStats />
    </div>
  </div>
</template>

<script setup>
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import TodoStats from './components/TodoStats.vue'
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background-color: #f3f4f6; /* abu muda */
  padding: 20px;
}

.todo-card {
  background: #ffffff;
  border-radius: 16px;
  padding: 32px;
  width: 100%;
  max-width: 500px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
}

h1 {
  margin: 0;
  font-size: 28px;
  color: #4f46e5; /* indigo */
  text-align: center;
}

.subtitle {
  color: #6b7280; /* abu */
  font-size: 14px;
  text-align: center;
  margin-bottom: 24px;
}
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background: linear-gradient(to bottom right, #e0f2f1, #f0fdfa); /* warna lembut */
  padding: 20px;
}
</style>
