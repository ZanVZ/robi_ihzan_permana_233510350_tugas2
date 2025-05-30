<template>
  <div>
    <h2>Computed Property</h2>
    <input type="checkbox" v-model="hideCompleted" />
    <label> Sembunyikan yang selesai </label>
    <ul>
      <li v-for="todo in filteredTodos" :key="todo.id">
        {{ todo.text }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

const hideCompleted = ref(false);
const todos = ref([
  { id: 1, text: 'Tugas 1', completed: true },
  { id: 2, text: 'Tugas 2', completed: false },
]);

const filteredTodos = computed(() =>
  hideCompleted.value
    ? todos.value.filter((t) => !t.completed)
    : todos.value
);
</script>

<style scoped>
h2 {
  margin-bottom: 1rem;
  color: #007acc;
}
p {
  font-size: 1rem;
  line-height: 1.6;
}
</style>
