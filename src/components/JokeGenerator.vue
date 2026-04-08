<template>
  <div class="joke-generator">
    <p>{{ joke }}</p>
    <button @click="fetchJoke">Get New Joke</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      joke: ''
    };
  },
  methods: {
    async fetchJoke() {
      try {
        const response = await fetch('https://api.jokes.one/jod');
        const data = await response.json();
        this.joke = data.contents.jokes[0].joke.text;
      } catch (error) {
        console.error('Error fetching joke:', error);
      }
    }
  },
  mounted() {
    this.fetchJoke();
  }
};
</script>

<style scoped>
.joke-generator {
  text-align: center;
  margin-top: 20px;
}
button {
  margin-top: 10px;
  padding: 10px 20px;
  font-size: 16px;
}
</style>
