<template>
  <div class="container">
    <h2>Jokes</h2>
    <SearchJokes @search-text="searchText" />
    <Joke :joke="joke.joke" :id="joke.id" v-for="joke in jokes" :key="joke.id" />
  </div>
</template>

<script>
import axios from 'axios';
import Joke from '../../components/Joke.vue'
import SearchJokes from '../../components/SearchJokes.vue'

export default {
  components: {
    Joke, SearchJokes
  },
  methods: {
    async searchText(text){
      const config = {
        headers: {
          "Accept": "application/json",
        }
      }
      try {
        const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config)
        console.log('searchPing: ', res.data.results);
        this.jokes = res.data.results
      } catch (error) {
        console.log('err: ', error);
      }
    }
  },
  data(){
    return {
      jokes: [],
    }
  },
  head(){
    return {
      title: 'Dad Joke Repo',
      meta: [
        { 
          hid: 'description', 
          name: 'description', 
          content: 'Best place for corny dad-jokes' 
        }
      ]
    }
  },
  async created(){
    const config = {
      headers: {
        "Accept": "application/json",
      }
    }
    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config)
      console.log('ping: ', res.data.results);
      this.jokes = res.data.results
    } catch (error) {
      console.log('err: ', error);
    }

  }
}
</script>

<style>

</style>