<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-sm-6">
          <div class="app-title text-muted">
            <div class="app-title-container">
              <h1 class="display-4 mt-2">
                Eisenhower Matrix
                <small>Tool By: CodeRomeos</small>
              </h1>
            </div>
            <p class="font-weight-bold">be more productive.</p>
          </div>
          <hr />
        </div>
        <div class="col-sm-6">
          <p class="mt-3">
            Based on
            <strong>
              <a
                href="https://en.wikipedia.org/wiki/Time_management#The_Eisenhower_Method"
              >Eisenhower Matrix</a>:
            </strong> Using the Eisenhower Decision Principle, tasks are evaluated using the criteria important/unimportant and urgent/not urgent, and then placed in according quadrants in an Eisenhower Matrix.
          </p>
        </div>
      </div>
    </div>
    <Matrix />
  </div>
</template>

<script>
import Matrix from "./components/Matrix.vue";

export default {
  name: "app",
  components: {
    Matrix
  }
};
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
.app-title-container {
  position: relative;
  max-width: 27rem;
}
.app-title small {
  display: block;
  font-size: 0.7rem;
  font-weight: bold;
  position: absolute;
  right: 0.25rem;
  top: 4rem;
}
@media (max-width: 575.98px) {
  .app-title h1 {
    font-size: 30px;
    font-weight: bold;
    line-height: 1;
    margin-top: 20px;
  }
}
</style>
