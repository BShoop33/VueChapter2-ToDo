<template>
  <div>
    <!-- <h2>I'm a todo item</h2> -->
    <h2
      :class="{ complete: todo.complete, laundry: todo.name == 'Fold laundry' }"
    >
      {{ todo.name }}
    </h2>

    <!-- <button @click="handleClick">Mark Completed</button> -->
    <button @click="handleClick">{{ buttonText }}</button>
  </div>
</template>

<script>
export default {
  //accepts the item prop from ToDoList.vue
  props: ["todo"],

  /*an event listener that a listens for the handleClick method to be called. When called, this method then emits a
  status-change message to this particular todo item that is used in ToDoList.vue to call the handleStatusChange method.
  When that method is called, it changes the status of the todo item from complete to incomplete or vice versa  */
  methods: {
    handleClick() {
      this.$emit("status-change", this.todo);
    },
  },

  /*a computed property that returns a different button text of a todo item depending whether the item's status is
  complete or incomplete*/
  computed: {
    buttonText() {
      return this.todo.complete ? "Mark Incomplete" : "Mark Complete";
    },
  },
};
</script>

<style>
.complete {
  text-decoration: line-through;
}

.laundry {
  color: red;
}
</style>