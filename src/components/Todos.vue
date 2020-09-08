<template>
    <div>
        <div id="todos" v-bind:key="todo.id" v-for="todo in todos">
            <ul>
             <li>{{todo.id}} -- <h3>{{todo.title}}</h3>
                 &nbsp;<span class="alert" v-if="todo.completed == true">Done</span>
             </li>

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
        margin-left: 0;
    }
    .alert{
        color: white;
        margin-left: 5px;
        border-radius: 25px;
        background: #73AD21;
        padding: 5px;
        width: 10px;
        height: 10px;
    }
</style>