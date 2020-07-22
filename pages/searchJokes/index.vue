<template>
  <b-container class="main">
    <div class="card">
      <searchJokes v-on:search-joke="searchJokes"/>
      <Joke v-for="joke in jokes" :key="joke.id" :joke="joke.value"/>
    </div>
  </b-container>
</template>

<script>
import axios from "axios";
import searchJokes from "../../components/searchJokes";
import Joke from "../../components/Joke";

export default {
  components: {
    searchJokes,
    Joke
  },
  data() {
    return {
      jokes: []
    }
  },
  methods: {
    async searchJokes(text) {
      const config = {
        headers: {
          "Accept": "application/json"
        }
      }

      try {
         const res = await axios.get(`https://api.chucknorris.io/jokes/search?query=${text}`, config);

        this.jokes = res.data.result;
      } catch (err) {
        console.log(err);
      }
    }
  }
}
</script>

<style>
  .card {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    padding: 3rem;
    margin: 2rem;
  }
</style>