<template>
  <div class="container">

    <h2>About page</h2>
    <div class="row justify-content-center">
      <div class="col-10">
        <p>Corny dad joke generator</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head(){
    return{
      title: 'About this joke of a page...',
      meta: [
        { 
          hid: 'description', 
          name: 'description', 
          content: 'Best place for corny dad-jokes' 
        }
      ]
    }
  }

}
</script>

<style>

</style>