<template>
  <form @submit="submitForm">
    <label for="">Task</label>
    <input type="text" placeholder="Enter Task" v-model="text" />
    <label for="">Reminder</label>
    <select name="" id="" v-model="reminder">
      <option value="true">true</option>
      <option value="false">false</option>
    </select>
    <button>ADD TASK</button>
  </form>
</template>

<script>
  export default {
    name: "Form",
    data() {
      return {
        text: "",
        reminder: false,
      };
    },
    methods: {
      submitForm(e) {
        e.preventDefault();
        if (!this.text) {
          return alert("plese enter a text");
        }
        const newTask = {
          text: this.text,
          date: new Date().toDateString(),
          reminder: false,
        };

        console.log(newTask);

        this.$emit("add-task", newTask);

        this.text = "";
      },
    },
  };
</script>

<style scoped>
  form {
    width: 350px;
    margin: auto;
    background: rgba(0, 0, 0, 0.05);
    padding: 20px;
  }

  form label {
    width: 100%;
    display: block;
    font-size: 18px;
    margin-bottom: 10px;
  }
  form input {
    width: 95%;
    font-size: 18px;
    margin-bottom: 20px;
    outline: none;
    padding: 5px;
  }
  form select {
    width: 100%;
    font-size: 18px;
    padding: 5px;
    margin-bottom: 10px;
  }
  form button {
    width: 100%;
    font-size: 18px;
    padding: 5px;
    cursor: pointer;
    color: white;
    background: black;
  }
</style>
