<template>
  <form @submit="submitForm">
    <h3>Add Task</h3>
    <input
      type="text"
      placeholder="Add Task"
      id="task"
      v-model="task"
      class="form-control"
    />
    <select v-model="reminder">
      <option value="true">True</option>
      <option value="false">False</option>
    </select>
    <button type="submit">Submit</button>
  </form>
</template>

<script>
  export default {
    name: "Form",
    data() {
      return {
        task: "",
        reminder: "true",
      };
    },
    methods: {
      submitForm(e) {
        e.preventDefault();
        if (!this.task) {
          return alert("Please add task");
        }

        const newTask = {
          text: this.task,
          date:
            new Date().toDateString() + " | " + new Date().toLocaleTimeString(),
          reminder: this.reminder === "true",
        };

        console.log(newTask);
        this.$emit("add-task", newTask);

        // Clear the form after submission
        this.task = "";
        this.reminder = "true";
      },
    },
  };
</script>

<style scoped></style>
