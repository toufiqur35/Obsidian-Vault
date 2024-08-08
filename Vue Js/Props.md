In Vue.js, **props** (short for properties) are a way to pass data from a parent component to a child component. They are a fundamental part of how components communicate and interact with each other in Vue applications. This guide will explain how to define, pass, and use props in Vue.js 3.

### What are Props?

Props are custom attributes that you can register on a component. When a value is passed to a prop, the child component receives it as a property that can be used in its template or logic.

### Defining Props in a Component

In Vue.js 3, you can define props in a component using an object within the `defineProps` or `props` option in the `setup` function or the component's options, respectively. Here’s how you can define props in both the Options API and the Composition API.

create title props components:
```vue
<script setup>
import { defineProps } from 'vue';

defineProps({
  title: {
    type: String,
    default: 'Become a Vue dev',
  },
  subtitle: {
    type: String,
    default: 'Find the Vue job that fits your skills and needs',
  },
});
</script>
```

use props components
```html
<script setup>
import Title from './components/Title.vue';
</script>

<template>
  <Hero title="Test Title" subtitle="Test Subtitle" />
</template>
```