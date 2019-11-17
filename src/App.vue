<template>
  <div id="app">
    <!-- <router-view/> -->
    <Header></Header>
    <TodoInput v-on:addTodo="addTodo"></TodoInput>
    <TodoList v-bind:propsdata="todoItems" @removeTodo="removeTodo"></TodoList>
    <Footer v-on:removeAll="clearAll"></Footer>
    
  </div>
</template>

<script>
import Header from './components/Header.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import Footer from './components/Footer.vue'
export default {
  // name: 'App'
  data () {
    return {
      todoItems: []
    }
  },
  created() {
    if (localStorage.length > 0) {
      for(var i=0; i<localStorage.length; i++) {
        this.todoItems.push(localStorage.key(i))
      }
    }
  },
  methods: {
    addTodo (todoItem) {
      localStorage.setItem(todoItem, todoItem)
      this.todoItems.push(todoItem)
    },
    removeTodo (todoItem, index) {
      localStorage.removeItem(todoItem)
      this.todoItems.splice(index, 1)
    },
    clearAll () {
      localStorage.clear()
      this.todoItems = []
    }
  },
  components: {
    'Header': Header,
    'TodoInput': TodoInput,
    'TodoList': TodoList,
    'Footer': Footer,
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
