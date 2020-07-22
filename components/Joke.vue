<template>
  <b-card class="mb-1">
    <b-card-text>
      {{ joke }}
    </b-card-text>
  </b-card>
</template>

<script>
export default {
  name: "Joke",
  props: ["joke"]
}
</script>

<style>
  .joke {
    padding: 1rem;
    border: 1px dotted #ccc;
    margin: 1rem 0;
  }
</style>