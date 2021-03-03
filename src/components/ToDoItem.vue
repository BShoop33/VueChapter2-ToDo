<template>
  <div>
    <!-- <h2>I'm a todo item</h2> -->
    <h2 :class="{ completed: todo.complete }">{{ todo.name }}</h2>
    <button @click="handleClick">Mark Completed</button>
  </div>
</template>

<script>
export default {
  props: ["todo"],

  methods: {
    handleClick() {
      this.$emit("status-change", this.todo);
    },
  },
};
</script>

<style>
.completed {
  text-decoration: line-through;
}
</style>