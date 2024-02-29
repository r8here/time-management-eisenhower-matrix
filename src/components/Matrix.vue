<template>
    
  <div class="container mt-3 mb-5">
    
    <div class="row">
        <Tasklist />
        <div class="col-sm-12 col-md-6">
            <tasks taskTitle='Do first' group-name='doFirst' background-class='bg-success' text-color-class='text-white'/>
        </div>
        <div class="col-sm-12 col-md-6">
            <tasks taskTitle='Schedule' group-name='schedule' background-class='bg-primary' text-color-class='text-white'/>
        </div>
        <div class="col-sm-12 col-md-6">
            <tasks taskTitle='Delegate' group-name='delegate' background-class='bg-warning'/>
        </div>
        <div class="col-sm-12 col-md-6">
            <tasks taskTitle='Trivial' group-name='trivial' background-class='bg-danger' text-color-class='text-white'/>
        </div>
    </div>
  </div>
</template>

<script>
import Tasks from './Tasks'
export default {
    name: 'EisenhourMatrix',
    components: {
       Tasks
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
