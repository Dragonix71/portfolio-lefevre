<!-- src/App.vue -->
<template>
  <div id="app">
    <BaseLayout />
  </div>
</template>

<script>
import BaseLayout from './components/BaseLayout.vue';

export default {
  name: 'App',
  components: {
    BaseLayout,
  },
};
</script>

<style>
html, body, #app {
  height: 100%;
  margin: 0;
}

h1 {
  margin: 0;
  padding: 0.5rem;
  font-size: 2rem;
}

p {
  margin: 0;
  padding: 0.5rem;
  font-size: 1rem;
}

#app {
  width: 100%;
  background: radial-gradient(#000B78, #474F9E);
  overflow-y: auto;
}
</style>
