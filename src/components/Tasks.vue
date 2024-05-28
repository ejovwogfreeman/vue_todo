<template>
  <div class="task-container">
    <div v-for="task in tasks">
      <h3>{{ task.text }}</h3>
      <small>{{ task.date }}</small>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Tasks",
    props: {
      tasks: Array,
    },
  };
</script>

<style scoped>
  .task-container {
    width: 400px;
    margin: auto;
  }
</style>
