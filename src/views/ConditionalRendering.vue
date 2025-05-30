<template>
  <div>
    <h2>Conditional Rendering</h2>
    <button @click="toggle">Toggle</button>
    <h3 v-if="awesome">Vue is awesome!</h3>
    <h3 v-else>Oh no 😢</h3>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const awesome = ref(true);
function toggle() {
  awesome.value = !awesome.value;
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
