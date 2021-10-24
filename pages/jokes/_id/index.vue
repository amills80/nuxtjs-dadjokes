<template>
  <div class="container">
    <nuxt-link to="/jokes">Back to Jokes</nuxt-link>
    <h5>{{joke}}</h5>
    <!-- <p class="lead">
      {{$route.params.id}}
    </p> -->
  </div>
</template>

<script>
import axios from "axios";
export default {
  data(){
    return {
      joke:{}
    }
  },
  async created(){
    let id = this.$route.params.id;
    console.log('testid: ', id);
    const config = {
      headers: {
        "Accept": "application/json"
      }
    }
    try {
      const res = await axios.get(`/api/j/${id}`, config);
      // const res = await axios.get(`https://icanhazdadjoke.com/j/${id}`, config)
      console.log('ping: ', res.data);
      this.joke = res.data.joke
    } catch (error) {
      console.log('err: ', error);
    }

  }
}
</script>

<style>

</style>