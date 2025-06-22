<template>
  <ul class="todo-list">
    <li v-for="todo in store.todos" :key="todo.id" class="todo-item">
      <label class="todo-label">
        <input
          type="checkbox"
          :checked="todo.done"
          @click="toggleTodo(todo.id)"
          class="checkbox"
        />
        <span :class="{ done: todo.done }">{{ todo.text }}</span>
      </label>
      <button @click="store.removeTodo(todo.id)" class="delete-btn" title="Hapus tugas">
        <!-- Ikon SVG Trash -->
        <svg xmlns="http://www.w3.org/2000/svg" class="icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6M9 7h6m-6 0V5a2 2 0 012-2h2a2 2 0 012 2v2" />
        </svg>
      </button>
    </li>
  </ul>
</template>

<script setup>
import { useTodoStore } from '../stores/todoStore'
const store = useTodoStore()

const toggleTodo = (id) => {
  store.toggleTodo(id)
}
</script>

<style scoped>
.todo-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 14px;
}

/* Item card */
.todo-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 14px 18px;
  background: #e0f7f4;
  border-left: 6px solid #14b8a6;
  border-radius: 12px;
  transition: all 0.2s ease;
}

.todo-item:hover {
  background: #ccf2ef;
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.05);
}

/* Label & Text */
.todo-label {
  display: flex;
  align-items: center;
  gap: 12px;
  font-size: 16px;
  color: #1e293b;
}

.todo-label span.done {
  text-decoration: line-through;
  color: #94a3b8;
}

/* Checkbox styling */
.checkbox {
  width: 18px;
  height: 18px;
  accent-color: #14b8a6;
  cursor: pointer;
}

/* Tombol Hapus */
.delete-btn {
  background: none;
  border: none;
  cursor: pointer;
  color: #ef4444;
  transition: color 0.2s ease;
}

.delete-btn:hover {
  color: #dc2626;
}

.icon {
  width: 20px;
  height: 20px;
}
</style>
