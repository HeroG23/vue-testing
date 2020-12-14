<template>
  <ToDoList v-bind="todos"/>
  <CreateToDo v-on:add-todo="addTodo"/>
</template>

<script>
import ToDoList from './components/ToDoList.vue';
import CreateToDo from './components/CreateToDo.vue';


export default {
  name: 'App',
  components: {
    ToDoList,
    CreateToDo
  },
  methods:{
    addTodo(title){
      this.todos.push({
        title,
        done: false,
      })
    }
  },
  data(){
    return{
      todos:[{
        title: 'Todo A',
        project: 'Project A',
        done: false,
      },
      {title: 'Todo B',
      project: 'Project B',
      done: false,
      },
      {
        title: 'Todo C',
        project: 'Project C',
        don: true,
      }],
    }
  }
};
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
