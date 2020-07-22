<template>
  <b-container>
    <b-card>
      <searchJokes v-on:search-joke="searchJokes"/>
      <Joke v-for="joke in jokes" :key="joke.id" :joke="joke.value"/>
    </b-card>
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
    padding: 2rem;
    margin: 2rem auto;
  }
</style>