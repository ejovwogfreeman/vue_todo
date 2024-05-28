<script>
  import Navbar from "./components/Navbar.vue";
  import Tasks from "./components/Tasks.vue";

  export default {
    name: "App",
    components: {
      Navbar,
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
  };
</script>

<template>
  <Navbar />
  <Tasks :tasks="tasks" />
</template>

<style></style>
