<template>
  <div>
    <SearchJokes @search-text="searchText" />
    <SingleJoke
      v-for="joke in jokes"
      :id="joke.id"
      :key="joke.id"
      :joke="joke.joke"
    />
  </div>
</template>

<script>
import axios from 'axios'
import SingleJoke from '../../components/SingleJoke'
import SearchJokes from '~/components/SearchJokes'
export default {
  components: {
    SingleJoke,
    SearchJokes,
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
          content: 'Best place for corny dad jokes',
        },
      ],
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json',
      },
    }
    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config)
      this.jokes = res.data.results
    } catch (error) {
      // eslint-disable-next-line no-console
      console.log('error', error)
    }
  },
  methods: {
    async searchText(text) {
      const config = {
        headers: {
          Accept: 'application/json',
        },
      }
      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        )
        this.jokes = res.data.results
      } catch (error) {
        // eslint-disable-next-line no-console
        console.log('error', error)
      }
    },
  },
}
</script>

<style lang="scss" scoped></style>
