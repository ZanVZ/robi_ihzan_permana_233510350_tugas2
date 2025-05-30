<template>
  <div>
    <h2>Form Bindings</h2>
    <input v-model="text" placeholder="Ketik sesuatu..." />
    <p>Kamu mengetik: {{ text }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const text = ref('');
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
