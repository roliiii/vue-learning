<template>
    <div>
        <div v-bind:key="todo.id" v-for="(todo, index) in todos" >
            <TodoItem :todo="todo" :index="index" />
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
