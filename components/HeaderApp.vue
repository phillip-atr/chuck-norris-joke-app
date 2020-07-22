<template>
  <b-navbar toggleable="lg" type="dark" variant="dark">
    <b-navbar-brand href="#">Chuck Norris Jokes App</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav class="ml-auto">
        <b-nav-item href="/">Home</b-nav-item>
        <b-nav-item href="/searchJokes">Search Jokes</b-nav-item>
      </b-navbar-nav>
    </b-collapse>

  </b-navbar>
</template>

<script>
export default {
  name: "HeaderApp"
}
</script>

<style>
  .items {
    padding: 0 1.5rem;
  }

  .developed-by {
    color: white;
  }
</style>