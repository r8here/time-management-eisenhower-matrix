<template>
<div class="card text-white mb-3" :class='backgroundClass'>
    <div class="card-header">{{ taskTitle }}</div>
    <div class="card-body">
        <div class="h-100">
                <ul class="list-group list-group-flush p-0">
                <li class="list-group-item mb-1 bg-transparent p-1">
                    <input class="rounded-0 form-control form-control-sm" @keyup.enter="addTask" type="text" v-model="newTask" placeholder="Add Task">
                </li>
                <li class="list-group-item mb-1 bg-transparent p-1" v-for="task in tasks" :key='task.taksItem'>
                    <div v-if="task.edit == false">
                    <label @dblclick="task.edit = true" class="mb-0 p-1">
                        {{ task.taskItem }}
                    </label>
                    </div>
                    <input class="rounded-0 form-control form-control-sm" v-else type="text" v-model="task.taskItem" placeholder="Edit Task" @focusout="task.edit = false">
                </li>
            </ul>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'Tasks',
    props: {
        'taskTitle': String,
        'backgroundClass': String
    },
    data(){
       return{
           tasks: [],
           newTask: ''
       }
   },

  methods: {
    created(){
        tasks.length < 1
        console.log(this.tasks.length);
    },
    addTask: function(){
        this.tasks.push({
            taskItem: this.newTask,
            edit: false
        })
        this.newTask = '';
    }
  }
}
</script>

<style scoped>
input,
.list-group-item > div{
    background: #ffffff4f;
    border: 0;
}
</style>


