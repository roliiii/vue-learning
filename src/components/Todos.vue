<template>
    <div>
        <div v-bind:key="todo.id" v-for="(todo, index) in todos" >
            <h3>{{todo.title}} - {{index}}</h3>
        </div>
    </div>
</template>

<script>
export default {
    name: "Todos",
    props: ["todos"]
}
</script>

<style scoped>

</style>
