<template>
  <div id="app">
    <img src="./assets/logo.png">
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:create-todo="addTodo"></create-todo>
  </div>
</template>

<script>
import TodoList from './components/TodoList'
import CreateTodo from './components/CreateTodo'

export default {
  name: 'App',
  components: {
    CreateTodo,
    TodoList
  },
  data () {
    return {
      todos: [
        {
          id: 1,
          title: 'Todo A',
          project: 'Project A',
          done: false
        },
        {
          id: 2,
          title: 'Todo B',
          project: 'Project B',
          done: true
        },
        {
          id: 3,
          title: 'Todo C',
          project: 'Project C',
          done: false
        }
      ]
    }
  },
  methods: {
    addTodo (todo) {
      this.todos.push(todo)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
