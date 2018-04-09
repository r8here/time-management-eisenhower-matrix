<template>
  <div class="container my-5">
    <div class="row">
        <div class="col-sm-12 col-md-6">
            <div class="card text-white bg-success mb-3">
                <div class="card-header">Do First</div>
                <div class="card-body">
                    <div class="h-100">
                         <ul class="list-group list-group-flush p-0">
                            <li class="list-group-item mb-1 bg-dark p-1" v-for="task in tasks">
                               <div v-if="task.edit == false">
                                <label @dblclick="task.edit = true" class="mb-0">
                                    {{ task.title }}
                                </label>
                               </div>
                                <input @keyup.enter="addTask" type="text" v-model="newTask" v-if="task.edit == true" placeholder="edit" value="">
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
        <!-- <div class="col-sm-12 col-md-6">
            <div class="card text-white bg-primary mb-3">
                <div class="card-header">Schedule</div>
                <div class="card-body">
                    <div class="h-100">
                         <ul class="list-group list-group-flush p-0">
                            <li class="list-group-item mb-1 bg-dark p-1" :bind="task in tasks">
                                <input type="text" class="w-100 border-0">
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div> -->
    </div>
    <!-- <div class="row">
        <div class="col-sm-12 col-md-6">
            <div class="card text-white bg-warning mb-3">
                <div class="card-header">Delegate</div>
                <div class="card-body">
                    <div class="h-100">
                         <ul class="list-group list-group-flush p-0">
                            <li class="list-group-item mb-1 bg-dark p-1" :bind="task in tasks">
                                <input type="text" class="w-100 border-0">
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-sm-12 col-md-6">
            <div class="card text-white bg-danger mb-3">
                <div class="card-header">Trivial</div>
                <div class="card-body">
                    <div class="h-100">
                         <ul class="list-group list-group-flush p-0">
                            <li class="list-group-item mb-1 bg-dark p-1" :bind="task in tasks">
                                <input type="text" class="w-100 border-0">
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div> -->
  </div>

</template>

<script>
export default {
  name: 'Matrix',
  props: ['todos'],
   data(){
       return{
           tasks: [{'title': 'some task', 'edit': false}],
           newTask: '',
           editTask: null
       }
   },
  methods: {
    addTask: function(){
        this.tasks.push({
            taskItem: this.newTask
        })
        this.newTask = '';
        // completed: false,
    },
    editTask: function(task){
        this.editTask = task;
        // console.log(task);
    }
  },
  watch:{
      todo: function(todo){
        console.log(this.todo);
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
input{
    width: 100%;
    background: #3dca54;
    border: 0;
}
</style>
