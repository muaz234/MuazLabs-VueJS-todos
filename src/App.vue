f<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <Todos v-bind:todos="todos_data"  />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Todos from "./components/Todos";
const axios = require('axios');
export default {
  name: 'App',
  data () {
    return {
      todos_data: []
    }

  },
  components: {
    Todos
  },
  mounted() {
    this.getTodos()
  },
  methods: {
    getTodos: function () {
     axios.get('https://jsonplaceholder.typicode.com/todos')
         .then((response) => this.todos_data = response.data)
         .catch(err => console.log(err));
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
