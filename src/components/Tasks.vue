<template>
<div class="card mb-3" :class="[backgroundClass, textColorClass]">
    <div class="card-header">{{ taskTitle }}
        <div class="float-right">
            Total tasks <span class="badge badge-light">{{ tasks.length }}</span> Pending tasks <span class="badge badge-light">{{ pendingCount }}</span>
        </div>
    </div>
    <div class="card-body">
        <div class="h-100">
            <ul class="list-group list-group-flush p-0">
                <li class="list-group-item mb-1 bg-white p-1">
                    <input class="rounded-0 form-control form-control-sm" @keyup.enter="addTask" type="text" v-model="newTask" placeholder="Add Task">
                </li>
                <li class="list-group-item task mb-1 bg-transparent p-0" v-for="(task, index) in tasks" :key='index'>
                    <div v-if="task.edit == false">
                    <label @dblclick="task.edit = true" class="mb-0 p-1" :class="{ 'done': task.status }">
                        <input type="checkbox" aria-label="Checkbox for following text input" @click="task.status = !task.status" :checked="task.status"> {{ task.taskItem }}
                    </label>
                    <div class="action float-right">
                        <!-- <button type='button' class="btn badge badge-dark mr-2" @click="task.status = !task.status">{{ task.status ? 'Mark as not done' : 'Mark as done' }}</button> -->

                        <button type="button" class="btn badge badge-danger mr-2" @click="removeTask(index)">X</button>
                    </div>
                    </div>
                    <input class="rounded-0 form-control form-control-sm" v-else type="text" v-model="task.taskItem" placeholder="Edit Task" @focusout="task.edit = false" @keyup.enter="task.edit = false">
                </li>
            </ul>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'TaskList',
    props: {
        'taskTitle': String,
        'backgroundClass': String,
        'groupName': { required: true },
        'textColorClass': { default: 'text-dark' }
    },
    data(){
        return{
            tasks: [],
            newTask: ''
        }
    },
    mounted() {
        if(localStorage.getItem(this.groupName)) {
            this.tasks = JSON.parse(localStorage.getItem(this.groupName)).tasks;
        }
    },
    watch: {
        tasks: {
            handler() {
                localStorage.setItem(this.groupName, JSON.stringify({ tasks: this.tasks }));
            },
            deep: true
        }
    },
    computed: {
        pendingCount() {
            var count = 0;
            this.tasks.forEach(function(task) {
                if(!task.status) {
                    count++;
                }
            });
            return count;
        }
    },
    methods: {
        addTask: function(){
            if(this.newTask !== '') {
                this.tasks.push({
                    taskItem: this.newTask,
                    edit: false,
                    status: false
                })
                this.newTask = '';
            }
        },
        removeTask: function(index){
            if(confirm('Remove task?')) {
                this.tasks.splice(index, 1)
            }
        }
    }
}
</script>

<style scoped>
input,
.list-group-item > div{
    border: 0;
}

.task.list-group-item div{
    background: #00000045;
}

.card-body{
    max-height: 250px;
    overflow: hidden;
    overflow-y: auto;
}
.done {
    text-decoration: line-through;
}

.bg-warning label {
    color: #fff !important
}
</style>


