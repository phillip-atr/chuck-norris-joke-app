<template>
  <div class="card">
    <b-form-textarea id="textarea-plaintext" class="joke-area" plaintext :value="joke"></b-form-textarea>
    <b-form @submit.prevent="onSubmit" inline>
      <label class="mb-2 mr-sm-2 mb-sm-0" for="category">Choose a category </label>
        <b-form-select class="mb-2 mr-sm-2 mb-sm-0" v-model="selected" :options="categories">
          <template v-slot:first>
            <b-form-select-option :value="null" disabled>Please select an category</b-form-select-option>
          </template>
        </b-form-select>
      <b-button class="mb-2 mr-sm-2 mb-sm-0" type="submit" variant="success">Generate</b-button>
      <label class="mb-2 mr-sm-2 mb-sm-0" for="category"> or Generate random joke </label>
      <b-button class="mb-2 mr-sm-2 mb-sm-0" @click.prevent="generateRandom" variant="outline-primary">Generate</b-button>
    </b-form>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "DisplayJokes",
  data() {
    return {
      joke: '',
      selected: null,
      categories: []
    }
  },
  async created() {
    const config = {
      headers: {
        "Accept": "application/json"
      }
    }

    try {
      const res = await axios.get("https://api.chucknorris.io/jokes/random", config);
      const categories = await axios.get("https://api.chucknorris.io/jokes/categories", config);
      
      this.joke = res.data.value;
      this.categories = categories.data;
    } catch (err) {
      console.log(err);
    }
  },
  methods: {
    async generateRandom() {
      const config = {
        headers: {
          "Accept": "application/json"
        }
      }

      try {
        const res = await axios.get("https://api.chucknorris.io/jokes/random", config);
        
        this.joke = res.data.value;
      } catch (error) {
        console.log(err);
      }
    },
    async onSubmit() {
      const config = {
        headers: {
          "Accept": "application/json"
        }
      }
      
      try {
        if (this.selected != null) {
          const res = await axios.get(`https://api.chucknorris.io/jokes/random?category=${this.selected}`, config);

          this.joke = res.data.value;
        }else {
          alert("Must Select a category! or Click Random Generate Button.");
        }
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
    text-align: center;
    padding: 3rem;
    margin: 2rem;
  }
</style>