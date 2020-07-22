<template>
  <b-form @submit.prevent="onSubmit">
    <b-form-group>
      <b-form-input
      v-model="text"
      required
      placeholder="Search Jokes..."
      ></b-form-input>
    </b-form-group>
    <b-button type="submit" variant="outline-primary">Search Jokes</b-button>
  </b-form>
</template>

<script>
export default {
  name: "searchJokes",
  data() {
    return {
      text: ''
    }
  },
  methods: {
    async onSubmit() {
      this.$emit("search-joke", this.text);
      this.text = "";
    }
  }
}
</script>

<style>

</style>