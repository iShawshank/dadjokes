<template>
  <div>
    <h1 class="font-semibold text-4xl">About DadJokes</h1>
    <p>This is an app that displays corny dad jokes</p>
  </div>
</template>

<script lang="ts">
export default {
  head() {
    return {
      title: 'About the app',
      // Array of meta tags to add to page
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for corny dad jokes'
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
