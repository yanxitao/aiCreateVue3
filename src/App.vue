<template>
  <div id="app">
    <JokeGenerator />
  </div>
</template>

<script>
import JokeGenerator from './components/JokeGenerator.vue';

export default {
  name: 'App',
  components: {
    JokeGenerator,
  },
};
</script>

<style>
/* Add any necessary styles here */
</style>