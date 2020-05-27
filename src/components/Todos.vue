<template>
    <div>
        <p>Todos:</p>
        <div v-bind:key="todo.id" v-for="(todo, index) in todos" >
            <TodoItem :todo="todo" :index="index" v-on:del-todo="$emit('del-todo', todo.id)" />
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
    name: "Todos",
    props: ["todos"],
    components:{
        TodoItem
    }
}
</script>

<style scoped>

</style>
