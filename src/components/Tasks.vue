<template>
<div class="card text-white mb-3" :class='backgroundClass'>
    <div class="card-header">{{ taskTitle }} <span class='label label-info'>(No of tasks {{ tasks.length }})</span> <span class='label label-info'>(No of pending tasks {{ pendingCount }})</span></div>
    <div class="card-body">
        <div class="h-100">
            <ul class="list-group list-group-flush p-0">
                <li class="list-group-item mb-1 bg-white p-1">
                    <input class="rounded-0 form-control form-control-sm" @keyup.enter="addTask" type="text" v-model="newTask" placeholder="Add Task">
                </li>
                <li class="list-group-item mb-1 bg-transparent p-0" v-for="(task, index) in tasks" :key='index'>
                    <div v-if="task.edit == false">
                    <label @dblclick="task.edit = true" class="mb-0 p-1">
                        {{ task.status ? 'Done' : '' }} {{ task.taskItem }}
                    </label>
                    <div class="action float-right">
                        <button type='button' class="btn-sm btn btn-info mr-2" @click="task.status = !task.status">{{ task.status ? 'Mark as not done' : 'Mark as done' }}</button>

                        <button class="btn-sm btn btn-danger mr-2" @click="tasks.splice(index, 1)">X</button>
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
    name: 'Tasks',
    props: {
        'taskTitle': String,
        'backgroundClass': String,
        'groupName': { required: true }
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
.card-body{
    max-height: 250px;
    overflow: hidden;
    overflow-y: auto;
}
/*  */
</style>


