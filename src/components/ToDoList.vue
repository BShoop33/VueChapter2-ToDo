<template>
  <div>
    <h3>ToDo List</h3>
    <div v-for="item in todos" :key="item.id">
      <ToDoItem :todo="item" @status-change="handleStatusChange" />
    </div>
  </div>
</template>

<script>
import { todoItems } from "../data";
import ToDoItem from "./ToDoItem.vue";

export default {
  components: { ToDoItem },
  methods: {
    handleStatusChange(item) {
      item.complete = !item.complete;
    },
  },
  data() {
    return {
      todos: [...todoItems],
    };
  },
};
</script>

<style>
</style>