<template>
  <div>
    <h3>ToDo List</h3>
    <div v-for="item in todos" :key="item.id">
      <ToDoItem :todo="item" />
    </div>
  </div>
</template>

<script>
import { todoItems } from "../data";
import ToDoItem from "./ToDoItem.vue";

export default {
  components: { ToDoItem },
  data() {
    return {
      todos: [...todoItems],
    };
  },
};
</script>

<style>
</style>