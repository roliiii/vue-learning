<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
import Header from "./components/layout/Header.vue";
import AddTodo from "./components/AddTodo.vue";

export default {
  name: "App",
  components: {
    Header,
    AddTodo,
    Todos
  },
  data() {
    return {
      todos: [
        { id: 1, title: "todo1", completed: true },
        { id: 2, title: "todo2", completed: true },
        { id: 3, title: "todo3", completed: false }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(x => x.id != id);
    },
    addTodo(newTodo){
      this.todos = [...this.todos, newTodo]
    }
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
