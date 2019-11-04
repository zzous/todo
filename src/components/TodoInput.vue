<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" placeholder="Type what you have to do" @keyup.enter="addTodo">
    <!-- <button @click="addTodo">ADD</button> -->
    <span class="addContainer" @click="addTodo">
      <i class="addBtn fas fa-plus"></i>
    </span>
  </div>
</template>

<script>
export default {
  data () {
    return {
      newTodoItem: ''
    }
  },
  methods: {
    addTodo() {
      if (this.newTodoItem !== '') {
        // localStorage.setItem(this.newTodoItem, this.newTodoItem) 
        let value = this.newTodoItem && this.newTodoItem.trim();
        localStorage.setItem(value, value);
        this.clearInput()
      }
    },
    clearInput() {
      this.newTodoItem = '';
    }
  }
}
</script>

<style scoped>
  input:focus {
    outline: none;
  }
  .inputBox {
    height: 50px;
    line-height: 50px;
    border-radius: 50px;
    background: #fff;
  }
  .inputBox input {
    font-size: .9rem;
    border-style: none;
  }
  .addContainer {
    display: block;
    float: right;
    width: 3rem;
    border-radius: 0 5px 5px 0;
    background: linear-gradient(to right, #6478Fb #8763FB);
  }
  .addBtn {
    vertical-align: middle;
    color: #fff;
  }
</style>