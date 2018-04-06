<template>
  <div id="app">
    <div class="container">
      <div class="col-sm-12">
        <h1 class="display-3">Eisenhower Matrix</h1>
        <p class="lead"><strong>be More Productive.</strong></p>
        <hr>
      </div>
    </div>
    <Matrix/>
  </div>
</template>

<script>
import Matrix from './components/Matrix.vue'

export default {
  name: 'app',
  components: {
    Matrix
  }
}
</script>

<style>
#app {
  /* font-family: 'Avenir', Helvetica, Arial, sans-serif; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
</style>
