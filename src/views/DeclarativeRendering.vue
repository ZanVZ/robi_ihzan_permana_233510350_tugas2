<template>
  <div>
    <h2>Declarative Rendering</h2>
    <p>{{ message }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const message = ref('Vue secara otomatis meng-update DOM berdasarkan data!');
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
