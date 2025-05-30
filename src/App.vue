<template>
  <div class="app">
    <Sidebar @select-topic="selected = $event" />
    <div class="main-content">
      <component :is="currentComponent" />
    </div>
  </div>
</template>

<script setup>
import { ref, computed, defineAsyncComponent } from 'vue'
import Sidebar from './components/Sidebar.vue'

const selected = ref('DeclarativeRendering')

const componentsMap = {
  DeclarativeRendering: defineAsyncComponent(() => import('./views/DeclarativeRendering.vue')),
  AttributeBindings: defineAsyncComponent(() => import('./views/AttributeBindings.vue')),
  EventListeners: defineAsyncComponent(() => import('./views/EventListeners.vue')),
  FormBindings: defineAsyncComponent(() => import('./views/FormBindings.vue')),
  ConditionalRendering: defineAsyncComponent(() => import('./views/ConditionalRendering.vue')),
  ListRendering: defineAsyncComponent(() => import('./views/ListRendering.vue')),
  ComputedProperty: defineAsyncComponent(() => import('./views/ComputedProperty.vue')),
  LifecycleTemplateRefs: defineAsyncComponent(() => import('./views/LifecycleTemplateRefs.vue')),
  Watchers: defineAsyncComponent(() => import('./views/Watchers.vue')),
}

const currentComponent = computed(() => {
  return componentsMap[selected.value] || {
    template: '<div><p>Pilih topik dari sidebar.</p></div>',
  }
})
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
