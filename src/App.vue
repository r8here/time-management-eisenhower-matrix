<template>
  <div id="app" class="">
   
    <EisenhourMatrix />
    <div class="container-fluid">
      <div class="row">
        <div class="col-sm-4">
          <div class="app-title text-muted">
            <div class="app-title-container">
              <h1 class="display-4 mt-2">
                Eisenhower Matrix
              </h1>
              <p class="font-weight-bold">be super productive.</p>
            </div>
          </div>
        </div>
        <div class="col-sm-8">
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
    <div class="app-by">
      <a href="//coderomeos.com" class="text-white badge badge-gradient">Tool By: CodeRomeos</a>
    </div>
  </div>
</template>

<script>
import EisenhourMatrix from "./components/Matrix.vue";

export default {
  name: "app",
  components: {
    EisenhourMatrix
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

.app-title h1 { font-size: 2.5rem }

.app-by{
  width: 100%;
  text-align: center;
  border-bottom: 1px solid #000;
  line-height: 0.1em;
  margin: 0 0 2.5rem;
  height: 10px;
}
.app-by a {
  background-color: #d4418e;
  background-image: linear-gradient(315deg, #d4418e 0%, #0652c5 74%);
  padding: .2rem .4rem .3rem;
}
@media (max-width: 575.98px) {
  .app-title h1 {
    font-size: 1.8rem;
    line-height: 1;
    margin-top: 20px;
  }
  .app-title-container {
    text-align: center
  }
}
</style>
