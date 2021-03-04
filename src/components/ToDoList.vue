<template>
  <div>
    <h3>ToDo List</h3>
    <h4>There are {{ itemsRemaining }} items left to do today</h4>

    <!-- Iterates over the three items in the ToDoItem array using
    the id of each item as the key -->
    <div v-for="item in todos" :key="item.id">
      <!-- the :todo="item" portion is passing the item prop to ToDoItem.vue to tell it what to render. 
      The @status-change="handleStatusChange" portion invokes the handleStatusChange method to change
      the state of item status between complete or incomplete. That state is used by ToDoItem.vue to
      change the button text between "Marked Complete" and "Marked Incomplete"  -->
      <ToDoItem :todo="item" @status-change="handleStatusChange" />
    </div>
  </div>
</template>

<script>
import { todoItems } from "../data";
import ToDoItem from "./ToDoItem.vue";

export default {
  //renders the ToDoItem component (the item cards) imported from ToDoItem.vue
  components: { ToDoItem },

  //when invoked, changes the todo item status from complete to incomplete or vice versa
  methods: {
    handleStatusChange(item) {
      item.complete = !item.complete;
    },
  },

  //copies the array of todo items from data.js
  data() {
    return {
      todos: [...todoItems],
    };
  },

  //computed property that filters out todo items that are not completed
  computed: {
    itemsRemaining() {
      const items = this.todos.filter((todo) => !todo.complete);
      return items.length;
    },
  },
};
</script>

<style>
</style>