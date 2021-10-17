<template>
  <div class="container">
    <nuxt-link :to="'/jokes/'+id">
      <div class="mx-auto card">
        <div class="card-body">
          <h6 class="mb-0">{{joke}}</h6>
        </div>
      </div>

    </nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'Joke',
  props: ['joke', 'id']
}
</script>

<style>

</style>