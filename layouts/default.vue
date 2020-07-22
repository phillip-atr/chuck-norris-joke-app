<template>
  <div>
    <HeaderApp/>
    <Nuxt />
  </div>
</template>

<script>
import HeaderApp from "../components/HeaderApp";

export default {
  components: {
    HeaderApp
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1rem;
    line-height: 1.6;
    background: #f4f4f4;
  }
</style>
