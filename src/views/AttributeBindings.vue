<template>
  <div>
    <h2>Attribute Bindings</h2>
    <p :class="titleClass">Ini teks dengan binding class.</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const titleClass = ref('highlight');
</script>

<style>
.highlight {
  color: red;
  font-weight: bold;
}
</style>
