<template>
  <ol>
    <li v-for="todoItem in todoArr" :key="todoItem.id" class="todo-list-item">
      <span class="name">{{todoItem.name}}</span>
      <span class="delete" @click="deleteTodoItem(todoItem.id)">X</span>
    </li>
  </ol>
</template>

<script type="text/javascript">
  export default {
    props: {
        todoArr: {
            type: Array,
            required: true
        },
        deleteTodoItem: {
            type: Function,
            required: true
        }
    }
}
</script>

<style lang="scss" scoped>
  
</style>