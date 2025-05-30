<template>
  <div>
    <h2>Event Listeners</h2>
    <button @click="increment">Klik Saya ({{ count }})</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const count = ref(0);
function increment() {
  count.value++;
}
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
