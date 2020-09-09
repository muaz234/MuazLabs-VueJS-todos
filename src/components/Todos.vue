<template>
    <div>
        <div id="todos" v-bind:key="todo.id" v-for="todo in todos">
            <ul>
             <li>{{todo.id}} -- <h3>{{todo.title}}</h3>
                 &nbsp;<span class="alert" v-if="todo.completed == true">Done</span>
                 &nbsp;<span class="alert-pending" v-else>Pending</span>
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
    li {
        margin: 0;
        padding: 0;
        text-align: left !important;
    }
    h3 {
        display: inline;
        margin-left: 0;
    }
    .alert{
        color: white;
        margin-left: 5px;
        border-radius: 20px;
        background: #73AD21;
        padding: 3px;
        width: 8px;
        height: 8px;
    }

    .alert-pending{
      color: white;
      margin-left: 5px;
      border-radius: 20px;
      background: red;
      padding: 3px;
      width: 8px;
      height: 8px;
    }
</style>