<template>
  <div class="stats">
    ✅ Tugas belum selesai: <strong>{{ store.remaining }}</strong>
  </div>
</template>

<script setup>
import { useTodoStore } from '../stores/todoStore'
const store = useTodoStore()
</script>

<style scoped>
.stats {
  text-align: center;
  margin-top: 20px;
  font-size: 14px;
  color: #6b7280;
}

.stats strong {
  color: #4f46e5;
}
</style>
