<template>
  <div class="container my-5">
    <div class="row">
        <div class="col-sm-12 col-md-6">
            <Tasks taskTitle='Do first' backgroundClass='bg-success'/>
        </div>
        <div class="col-sm-12 col-md-6">
            <Tasks taskTitle='Schedule' backgroundClass='bg-primary'/>
        </div>
        <div class="col-sm-12 col-md-6">
            <Tasks taskTitle='Delegate' backgroundClass='bg-warning'/>
        </div>
        <div class="col-sm-12 col-md-6">
            <Tasks taskTitle='Trivial' backgroundClass='bg-danger'/>
        </div>
    </div>
  </div>
</template>

<script>
import Tasks from './Tasks.vue'
export default {
    name: 'Matrix',
    components: {
        Tasks
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    /**/
</style>
