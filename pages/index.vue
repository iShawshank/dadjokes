<template>
  <div>
    <h2>Welcome to the best corny dad jokes on the web</h2>
  </div>
</template>

<script lang="ts">
export default {
  head() {
    return {
      title: 'Welcome to Dad Jokes',
      // Array of meta tags to add to page
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for corny dad jokes',
        },
      ],
    }
  },
}
</script>
