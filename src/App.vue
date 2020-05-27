<template>
  <div id="app">
    <Header />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from './components/Todos.vue'
import Header from './components/layout/Header.vue'

export default {
  name: 'App',
  components: {
    Header,
    Todos
  }, 
  data(){
    return {
      todos:[
        {id:1,title:'todo1',completed:true},
        {id:2,title:'todo2',completed:true},
        {id:3,title:'todo3',completed:false},
      ]
    }
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(x => x.id!=id)
    }
  }
}
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
</style>
