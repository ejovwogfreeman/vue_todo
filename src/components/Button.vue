<template>
  <button v-bind:style="{ background: color }">{{ title }}</button>
</template>

<script>
  export default {
    name: "Button",
    props: {
      title: String,
      color: String,
    },
  };
</script>

<style scoped>
  button {
    font-size: 18px;
    padding: 7px 15px;
    cursor: pointer;
    border: none;
    outline: none;
    color: white;
  }
</style>
