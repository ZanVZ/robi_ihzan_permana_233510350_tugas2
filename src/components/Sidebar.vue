<template>
  <div class="sidebar">
    <h2>📘 Topik Vue</h2>
    <ul>
      <li
        v-for="(topic, i) in topics"
        :key="i"
        @click="selectTopic(topic.component)"
        :class="{ active: selected === topic.component }"
      >
        {{ topic.label }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const emit = defineEmits(['select-topic']);
const selected = ref('');

const topics = [
  { label: 'Declarative Rendering', component: 'DeclarativeRendering' },
  { label: 'Attribute Bindings', component: 'AttributeBindings' },
  { label: 'Event Listeners', component: 'EventListeners' },
  { label: 'Form Bindings', component: 'FormBindings' },
  { label: 'Conditional Rendering', component: 'ConditionalRendering' },
  { label: 'List Rendering', component: 'ListRendering' },
  { label: 'Computed Property', component: 'ComputedProperty' },
  { label: 'Lifecycle & Template Refs', component: 'LifecycleTemplateRefs' },
  { label: 'Watchers', component: 'Watchers' },
];

function selectTopic(componentName) {
  selected.value = componentName;
  emit('select-topic', componentName);
}
</script>

<style scoped>
.sidebar {
  width: 280px;
  background-color: #ffffff;
  border-right: 1px solid #ddd;
  padding: 2rem 1rem;
  box-shadow: 2px 0 5px rgba(0, 0, 0, 0.05);
}

.sidebar h2 {
  margin-bottom: 1rem;
  font-size: 1.3rem;
  color: #333;
}

.sidebar ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.sidebar li {
  padding: 0.6rem 1rem;
  margin-bottom: 0.5rem;
  cursor: pointer;
  border-radius: 6px;
  transition: background-color 0.2s;
}

.sidebar li:hover {
  background-color: #f0f0f0;
}

.sidebar li.active {
  background-color: #007acc;
  color: white;
}
</style>
