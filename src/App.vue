<template>
  <h1>Movies</h1>
  <Form />
</template>

<script>
import Form from "./components/Form.vue";
export default {
  name: "App",
  components: {
    Form: Form,
  },
};
</script>

<style lang="scss">
@import "./assets/theme/_variables.scss";

html,
body {
  background: $background-color;
  color: $primary-color;
  margin: 0;
  padding: 0;
  font-family: sans-serif;
}

h1 {
  text-align: center;
  padding-bottom: 0.5rem;
  border-bottom: 1px solid $primary-color;
}
</style>
