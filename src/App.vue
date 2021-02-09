<template>
  <div id="app">
    <p>App Todo</p>
    <NewTodo inputLabel="Todo " @onAddTodo="addTodo"/>
    <TodoList :todos="todoList" @onDelete="deleteTodo" @onFinish="finishTodo"/>
    <DeleteAllTodo @onDeleteAll="deleteAllTodo" />
  </div>
</template>

<script>
import NewTodo from './components/NewTodo'
import TodoList from './components/TodoList'
import DeleteAllTodo from './components/DeleteAllTodo'

export default {
  name: 'App',
  components: {
    NewTodo, 
    TodoList,
    DeleteAllTodo
  }, 
  data() {
    return {
      todoList: [], 
      nextId: 1
    }
  },
  methods: {
    addTodo(description) {
      this.todoList.push({
        id: this.nextId++, 
        todoDescription: description,
        finished: false
      })
    },
    deleteAllTodo() {
      this.todoList = []
    },
    deleteTodo(id) {
      this.todoList = this.todoList.filter(todo => todo.id !== id)
    },
    finishTodo(id) {
      this.todoList = this.todoList.map(todo => {
        if (todo.id === id) {
          todo.finished = !todo.finished
        }
        return todo
      })
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
