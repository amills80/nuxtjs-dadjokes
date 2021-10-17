<template>
  <form class="form-group" @submit.prevent="onSubmit">
    <!-- <div class="input-group">

    </div> -->
    <input type="text" name="search" v-model="text" placeholder="Search Jokes..." id="search">
    <input type="submit" value="Search">
  </form>
</template>

<script>
export default {
  name: "SearchJokes",
  data(){
    return {
      text: "",

    }
  },
  methods:{
    onSubmit: function(){
      this.$emit('search-text', this.text);
      this.text = '';
    }
  }
}
</script>

<style>

</style>