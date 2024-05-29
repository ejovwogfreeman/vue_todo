<script>
  import Navbar from "./components/Navbar.vue";
  import Tasks from "./components/Tasks.vue";
  import Form from "./components/Form.vue";

  export default {
    name: "App",
    components: {
      Navbar,
      Form,
      Tasks,
    },
    data() {
      return {
        tasks: [
          {
            text: "Meeting with doctor",
            date: "jun 5th 2024",
            remider: true,
          },
          {
            text: "Sudy vue js all day",
            date: "jun 6th 2024",
            remider: true,
          },
          {
            text: "Study Github",
            date: "july 20th 2024",
            remider: false,
          },
        ],
      };
    },
    methods: {
      addTask(task) {
        this.tasks = [task, ...this.tasks];
      },
      deleteTask(index) {
        this.tasks.splice(index, 1);
      },
    },
  };
</script>

<template>
  <Navbar />
  <Form @add-task="addTask" />
  <Tasks :tasks="tasks" @delete-task="deleteTask" />
</template>

<style></style>
