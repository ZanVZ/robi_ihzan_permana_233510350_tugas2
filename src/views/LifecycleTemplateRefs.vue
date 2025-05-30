<template>
  <div>
    <h2>Lifecycle dan Template Refs</h2>
    <input ref="inputRef" placeholder="Akan difokus saat mount" />
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';

const inputRef = ref(null);

onMounted(() => {
  inputRef.value.focus();
});
</script>

<style>
h2 {
  margin-bottom: 1rem;
  color: #007acc;
}
p {
  font-size: 1rem;
  line-height: 1.6;
}
</style>
