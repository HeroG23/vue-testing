<template>
  <div>
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <ToDo v-bind:todo="todo" v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo" />
  </div>
</template>

<script type = "text/javascript" >

import Todo from './Todo';

export default {
  props: ['todos'],
  components: {
    Todo,
  },
  methods:{
    delete(todo){
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex,1);
    },
    completeTodo(todo){
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = true;
    },
  }
};
</script>