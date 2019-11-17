<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" placeholder="Type what you have to do" @keyup.enter="addTodo">
    <!-- <button @click="addTodo">ADD</button> -->
    <span class="addContainer" @click="addTodo">
      <i class="addBtn">+</i>
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
        let value = this.newTodoItem && this.newTodoItem.trim();
        this.$emit('addTodo', value)
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
    cursor: pointer;
    border-radius: 0 5px 5px 0;
    background: linear-gradient(to right, #6478Fb #8763FB);
  }
  .addBtn {
    display: inline-block;
    vertical-align: middle;
    color: #333;
  }
</style>