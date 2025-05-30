<template>
  <div>
    <h2>Watchers</h2>
    <input v-model="name" placeholder="Nama" />
    <p>{{ greeting }}</p>
  </div>
</template>

<script setup>
import { ref, watch } from 'vue';

const name = ref('');
const greeting = ref('Halo!');

watch(name, (newVal) => {
  greeting.value = `Halo, ${newVal}!`;
});
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
