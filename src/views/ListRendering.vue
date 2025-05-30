<template>
  <div>
    <h2>List Rendering</h2>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        {{ todo.text }}
      </li>
    </ul>
  </div>
</template>

<script setup>
const todos = [
  { id: 1, text: 'Belajar Vue' },
  { id: 2, text: 'Buat Project ToDo' },
  { id: 3, text: 'Upload ke Netlify' },
];
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
