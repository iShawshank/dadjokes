<template>
 <header class="header flex justify-between items-center mb-4 pb-4">
  <h1 class="title text-5xl">Dad Jokes</h1>
  <ul class="flex">
    <li>
      <nuxt-link to="/">Home</nuxt-link>
    </li>
    <li>
      <nuxt-link to="/jokes">Jokes</nuxt-link>
    </li>
    <li>
      <nuxt-link to="/about">About</nuxt-link>
    </li>
  </ul>
 </header>
</template>

<script>
  export default {
    name: 'AppHeader'
  }
</script>

<style scoped>
  .header {
    border-bottom: 1px dotted #ccc;
  }
  .header .title {
    color: #526488;
  }

  .header a {
    display: inline-block;
    background: #333;
    color: #fff;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
  }
</style>
