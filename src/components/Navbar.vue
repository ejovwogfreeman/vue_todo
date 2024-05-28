<template>
  <div class="container">
    <div class="main-nav">
      <h1>Task Tracker</h1>
      <h2>V.0.0.1</h2>
    </div>
    <div class="nav">
      <h2>Toggle Form</h2>
      <Button title="Open" color="green" />
    </div>
  </div>
</template>

<script>
  import Button from "./Button.vue";
  export default {
    name: "Navbar",
    components: {
      Button,
    },
    props: {
      title: String,
    },
  };
</script>

<style scoped>
  h1,
  h2 {
    margin: 0px;
  }
  .container {
    width: 400px;
    margin: auto;
  }
  .main-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: tomato;
    color: #fff;
    padding: 20px;
  }
  .nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 20px;
  }
</style>
