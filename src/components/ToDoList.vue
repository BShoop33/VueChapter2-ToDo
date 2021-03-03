<template>
  <div>
    <h3>ToDo List</h3>
  </div>
</template>

<script>
import { todoItems } from "../data";

export default {
  data() {
    return {
      todos: [...todoItems],
    };
  },
};
</script>

<style>
</style>