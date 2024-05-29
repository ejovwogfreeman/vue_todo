<template>
  <div class="task-container">
    <div v-for="(task, index) in tasks" :key="index">
      <section class="div">
        <h3>{{ task.text }}</h3>
        <span @click="deleteTask(index)">x</span>
      </section>
      <small>{{ task.date }}</small>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Tasks",
    props: {
      tasks: {
        type: Array,
        required: true,
      },
    },
    methods: {
      deleteTask(index) {
        this.$emit("delete-task", index);
      },
    },
  };
</script>

<style scoped>
  .task-container {
    width: 400px;
    margin: auto;
    margin-top: 20px;
  }

  .task-container div {
    border: 1px solid rgba(0, 0, 0, 0.05);
    margin-bottom: 20px;
    padding: 20px;
  }

  .task-container div section {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .task-container div section span {
    color: red;
    font-size: 18px;
    cursor: pointer;
  }

  .task-container h3 {
    margin: 0px;
    margin-bottom: 5px;
  }
</style>
