<template>
  <div id="app">
    <h1>To Do List</h1>
    <AddTodo @add-todo:="addTodo"/>
    <hr>
    <TodoList v-if:="todos.length" v-bind:todos="todos" v-on:remove-todo="removeTodo"
    />
    <p v-else:>Задач ещё нет</p>
  </div>
</template>

<script>
import TodoList from '@/components/TodoList.vue'
import AddTodo from '@/components/AddTodo.vue'


export default {
  name: 'App',
  data() {
    return {
      todos: [
        {id: 1, title: 'начните работу с ToDoList', completed: false}
      ]
    }
  },
  methods:{
    removeTodo(id){
      this.todos = this.todos.filter(t => t.id !== id)
    },
    AddTodo(todo){
      this.todos.push(todo)
    }
  },
  components: {
    TodoList, AddTodo
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
