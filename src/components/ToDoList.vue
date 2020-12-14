<template>
  <div id="todo-container">
    <input type="text" v-model="todoText" id="todo-input"/>
    <button @click="addTodoItem" id="todo-delete">Add</button>
    <div id="todo-list"></div>
    <ToDoListItem v-bind:todo="todo" v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo" />
  </div>
</template>

<script>

import ToDoListItem from './ToDoListItem';

export default {
  name: 'TodoList',
  components: {
    ToDoListItem
  },
  data() {
    return {
      todoArr: [],
      todoText: "",
      id: 0
    }
  },
  methods: {
    addTodoItem() {
      this.id += 1

      const next = {id: this.id, name: this.todoText}
      this.todoArr.push(next)
    },
    deleteTodoItem(todoItemId) {
      this.todoArr = this.todoArr.filter(item => item.id !== todoItemId)
    }
  }
}
</script>

<style lang="sass" scoped>
#todo-container
  display: flex
  flex-direction: column
  align-items: center

#todo-list
  width: 300px
  border: 2px solid black
  margin-top: 15px
</style>