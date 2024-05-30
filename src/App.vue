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
        reminder: false,
        toggle: false,
        tasks: JSON.parse(localStorage.getItem("tasks")) || [],
      };
    },
    methods: {
      addTask(task) {
        this.tasks = [task, ...this.tasks];
        localStorage.setItem("tasks", JSON.stringify(this.tasks));
      },
      deleteTask(index) {
        this.tasks.splice(index, 1);
        localStorage.setItem("tasks", JSON.stringify(this.tasks));
      },
      setReminder(index) {
        this.tasks[index].reminder = !this.tasks[index].reminder;
        localStorage.setItem("tasks", JSON.stringify(this.tasks));
      },
      toggleForm() {
        this.toggle = !this.toggle;
      },
    },
  };
</script>

<template>
  <Navbar v-bind:toggle="toggle" @toggle-form="toggleForm" />
  <Form @add-task="addTask" :toggle="toggle" />
  <Tasks
    :tasks="tasks"
    @delete-task="deleteTask"
    @set-reminder="setReminder"
    v-bind:reminder="reminder"
  />
</template>

<style></style>
