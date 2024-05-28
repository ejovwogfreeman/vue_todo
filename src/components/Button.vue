<template>
  <button>{{ title }}</button>
</template>

<script>
  export default {
    name: "Button",
    props: {
      title: String,
    },
  };
</script>

<style scoped>
  button {
    font-size: 18px;
    padding: 7px 15px;
    cursor: pointer;
  }
</style>
