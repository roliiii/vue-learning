<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from ".././components/Todos.vue";
import AddTodo from ".././components/AddTodo.vue";
//import axios from "axios"

export default {
  name: "Home",
  components: {
    AddTodo,
    Todos
  },
  data() {
    return {
      todos: [
         { id: 1, title: "Vue-t tanulni", completed: true },
         { id: 2, title: "Gitet tanulni", completed: true },
         { id: 3, title: "kurento átnézése", completed: false }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      //axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      //.then(() => this.todos = this.todos.filter(x => x.id != id))
      //.catch(err => console.log(err))
      this.todos = this.todos.filter(x => x.id != id);
    },
    addTodo(newTodo){
      //const {title, completed} = newTodo
      //axios.post('https://jsonplaceholder.typicode.com/todos', {title,completed})
      //.then(res => this.todos = [...this.todos, res.data])
      //.catch(err => console.log(err))
      if(newTodo.title != ''){
        this.todos = [...this.todos, newTodo]
      }
    }
  },
  created(){
    //axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
    //.then(res=> this.todos = res.data)
    //.catch(err => console.log(err))
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn {
  display: inline-bloPck;
  border: none;
  background: #555;
  color: white;
  cursor: pointer;
  padding: 7px 20px;
}

.btn:hover {
  background: #666;
}
</style>
