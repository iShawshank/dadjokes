<template>
  <div>
    <SearchJokes @search-text="searchText"/>
    <Joke v-for="joke in jokes" :id="joke.id" :key="joke.id" :joke="joke.joke"/>
  </div>
</template>

<script>
  import axios from 'axios';
  import Joke from '../../components/Joke';
  import SearchJokes from '~/components/SearchJokes';
  export default {
    components: {
      Joke,
      SearchJokes
    },
    data() {
      return {
        jokes: [],
      }
    },
    head() {
      return {
        title: 'Dad Jokes',
        // Array of meta tags to add to page
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: 'Best place for corny dad jokes'
          }
        ]
      }
    },
    async created() {
      const config = {
        headers: {
          'Accept': 'application/json',
        }
      }
      try {
        const res = await axios.get('https://icanhazdadjoke.com/search', config);
        this.jokes = res.data.results;

      } catch (error) {
        console.log('error', error);
      }
    },
    methods: {
      async searchText(text) {
        const config = {
        headers: {
          'Accept': 'application/json',
        }
      }
      try {
        const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);
        this.jokes = res.data.results;
      } catch (error) {
        console.log('error', error);
      }
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>
