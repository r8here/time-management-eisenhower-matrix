<template>
  <div class="container my-5">
    <div class="row">
        <div class="col-sm-12 col-md-6">
            <tasks taskTitle='Do first' group-name='doFirst' background-class='bg-success'/>
        </div>
        <div class="col-sm-12 col-md-6">
            <tasks taskTitle='Schedule' group-name='schedule' background-class='bg-primary'/>
        </div>
        <div class="col-sm-12 col-md-6">
            <tasks taskTitle='Delegate' group-name='delegate' background-class='bg-warning'/>
        </div>
        <div class="col-sm-12 col-md-6">
            <tasks taskTitle='Trivial' group-name='trivial' background-class='bg-danger'/>
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
