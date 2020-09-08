<template>
    <div>
        <div id="todos" v-bind:key="todo.id" v-for="todo in todos">
            <ul>
             <li><span>{{todo.id}} -- <h3>{{todo.title}}</h3></span></li>
            </ul>
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
    #todos {
        margin: 0 auto;
        width: 30%;
        height: 50%;
    }
    h3 {
        display: inline;
        text-align: left !important;
    }
</style>