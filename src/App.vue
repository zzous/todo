<template>
  <div id="app">
    <!-- <router-view/> -->
    <Header></Header>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <Footer></Footer>
    
  </div>
</template>

<script>
import Header from './components/Header.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import Footer from './components/Footer.vue'
export default {
  // name: 'App'
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
