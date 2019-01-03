<template>
  <div id="app">
    <div class="container">
      <div class="col-sm-12 ">
        <div class="app-title">
          <h1 class="display-3">Eisenhower Matrix</h1>
          <p class="lead ml-1"><strong>be More Productive.</strong></p>
        </div>
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

<style lang="css" scoped>
  #app {
    /* font-family: 'Avenir', Helvetica, Arial, sans-serif; */
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    /* text-align: center;
    color: #2c3e50;
    margin-top: 60px; */
  }
  @media (max-width: 575.98px) {
    .app-title h1{
      font-size: 30px;
      font-weight: bold;
      line-height: 1;
      margin-top: 20px
    }
  }

</style>
