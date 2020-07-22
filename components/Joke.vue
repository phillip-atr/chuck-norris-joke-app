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
</style>