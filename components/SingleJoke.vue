<template>
  <nuxt-link :to="'jokes/' + id">
    <div class="joke">
      <p>{{ joke }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'SingleJoke',
  props: {
    joke: {
      type: String,
      required: true,
    },
    id: ID,
  },
}
</script>

<style scoped>
.joke {
  padding: 1rem;
  border: 1px dotted #ccc;
  margin: 1rem 0;
}
</style>
