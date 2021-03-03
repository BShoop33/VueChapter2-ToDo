<template>
  <div>
    <!-- <h2>I'm a todo item</h2> -->
    <h2>{{ todo.name }}</h2>
  </div>
</template>

<script>
export default {
  props: ["todo"],
};
</script>

<style>
</style>