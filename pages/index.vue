<template>
  <b-container class="main">
    <DisplayJokes />
  </b-container>
</template>

<script>
import DisplayJokes from "../components/DisplayJokes";

export default {
  components: {
    DisplayJokes
  }
}
</script>

<style>
  .main {
    margin: 2rem auto;
  }
</style>
