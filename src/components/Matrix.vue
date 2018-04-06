<template>
  <div class="container my-5">
    <div class="row">
        <div class="col-sm-12 col-md-6">
            <div class="card text-white bg-success mb-3">
                <div class="card-header">Do First</div>
                <div class="card-body">
                    <div class="h-100">
                        <ul class="list-group list-group-flush p-0">
                            <li class="list-group-item mb-1 bg-dark p-1" v-for="todo in todos">
                                <div v-show="todo.edit == false">
                                    <label class="w-100 m-0" @dblclick="todo.edit = true"> {{todo.title}} </label>
                                </div>
                                <input class="w-100 border-0 tsext-white" v-show="todo.edit == true" v-model="todo.title" v-on:blur="todo.edit=false; $emit('update')" @keyup.enter="todo.edit=false; $emit('update')">
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-sm-12 col-md-6">
            <div class="card text-white bg-primary mb-3">
                <div class="card-header">Schedule</div>
                <div class="card-body">
                    <div class="h-100">
                        <ul class="list-group list-group-flush p-0">
                            <li class="list-group-item mb-1 bg-dark p-1" v-for="todo in todos">
                                <div v-show="todo.edit == false">
                                    <label class="w-100 m-0" @dblclick="todo.edit = true"> {{todo.title}} </label>
                                </div>
                                <input class="w-100 border-0 tsext-white" v-show="todo.edit == true" v-model="todo.title" v-on:blur="todo.edit=false; $emit('update')" @keyup.enter="todo.edit=false; $emit('update')">
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="row">
        <div class="col-sm-12 col-md-6">
            <div class="card text-white bg-warning mb-3">
                <div class="card-header">Delegate</div>
                <div class="card-body">
                    <div class="h-100">
                        <ul class="list-group list-group-flush p-0">
                            <li class="list-group-item mb-1 bg-dark p-1" v-for="todo in todos">
                                <div v-show="todo.edit == false">
                                    <label class="w-100 m-0" @dblclick="todo.edit = true"> {{todo.title}} </label>
                                </div>
                                <input class="w-100 border-0 tsext-white" v-show="todo.edit == true" v-model="todo.title" v-on:blur="todo.edit=false; $emit('update')" @keyup.enter="todo.edit=false; $emit('update')">
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
                            <li class="list-group-item mb-1 bg-dark p-1" v-for="todo in todos">
                                <div v-show="todo.edit == false">
                                    <label class="w-100 m-0" @dblclick="todo.edit = true"> {{todo.title}} </label>
                                </div>
                                <input class="w-100 border-0 tsext-white" v-show="todo.edit == true" v-model="todo.title" v-on:blur="todo.edit=false; $emit('update')" @keyup.enter="todo.edit=false; $emit('update')">
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'Matrix',
  data(){
  return {
    todos:[{'title':'one value','edit':false},
          {'title':'one value','edit':false},
          {'title':'otro titulo','edit':false}],
    };
  },
  // methods: {
	// 	editTodo: function(todo) {
	// 	  this.editedTodo = todo;
	// 	},
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
