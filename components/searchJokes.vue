<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="text" placeholder="Search Jokes...">
    <input type="submit" value="Search Jokes">
  </form>
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