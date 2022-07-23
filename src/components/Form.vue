<template>
  <form v-for="(movie, i) in movies" :key="i">
    <h3>{{ movie.name }}</h3>
    <button
      type="button"
      v-on:click="movie.quantity -= 1"
      v-bind:disabled="movie.quantity <= 0"
    >
      -
    </button>
    <p>{{ movie.quantity }}</p>
    <button
      type="button"
      v-on:click="movie.quantity += 1"
      v-bind:disabled="movie.quantity >= movie.available"
    >
      +
    </button>
  </form>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      movies: [
        {
          name: "Avengers",
          available: 3,
          quantity: 0,
        },
        {
          name: "Terminator",
          available: 5,
          quantity: 0,
        },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
@import "../assets/theme/_variables.scss";

form {
  background-color: rgba($background-color, 0.7);
  border: 1px solid $primary-color;
  border-radius: 0.5rem;
  box-shadow: 0 0 4px rgb(233, 233, 233);
  max-width: 600px;
  margin: 0 auto;
  margin-bottom: 1rem;
  text-align: center;
  padding: 1rem;
}

p {
  display: inline-block;
  margin: 0 1rem;
}

button {
  padding: 0.5rem 1rem;
  border: 1px solid $primary-color;
  border-radius: 0.5rem;
  background-color: inherit;
  color: $primary-color;
  font-size: 1.4rem;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.3s ease, color 0.3s ease;

  &:hover {
    background-color: $primary-color;
    color: $background-color;
  }

  &[disabled] {
    opacity: 0.5;
  }

  &:focus {
    box-shadow: 0 0 4px rgb(233, 233, 233);
  }
}
</style>
