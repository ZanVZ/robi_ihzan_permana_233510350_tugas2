<template>
  <div class="app">
    <Sidebar @select-topic="selected = $event" />
    <div class="main-content">
      <component :is="currentComponent" />
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import Sidebar from './components/Sidebar.vue';

import DeclarativeRendering from './views/DeclarativeRendering.vue';
import AttributeBindings from './views/AttributeBindings.vue';
import EventListeners from './views/EventListeners.vue';
import FormBindings from './views/FormBindings.vue';
import ConditionalRendering from './views/ConditionalRendering.vue';
import ListRendering from './views/ListRendering.vue';
import ComputedProperty from './views/ComputedProperty.vue';
import LifecycleTemplateRefs from './views/LifecycleTemplateRefs.vue';
import Watchers from './views/Watchers.vue';

const selected = ref('DeclarativeRendering');

const componentsMap = {
  DeclarativeRendering,
  AttributeBindings,
  EventListeners,
  FormBindings,
  ConditionalRendering,
  ListRendering,
  ComputedProperty,
  LifecycleTemplateRefs,
  Watchers,
};

const currentComponent = computed(() => componentsMap[selected.value]);
</script>

<style>
body {
  margin: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f9f9f9;
}

.app {
  display: flex;
  height: 100vh;
}

.main-content {
  flex: 1;
  padding: 2rem;
  overflow-y: auto;
}
</style>
