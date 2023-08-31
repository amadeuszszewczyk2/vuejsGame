<template>
  <div id="app">
    <h1>Guess the Number!</h1>
    <p>We have selected a random number between 1 and 100. Try to guess it!</p>
    <input type="number" v-model="guess" />
    <button @click="checkGuess">Guess</button>
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numberToGuess: Math.floor(Math.random() * 100) + 1,
      guess: null,
      message: "",
    };
  },
  methods: {
    checkGuess() {
      if (this.guess === this.numberToGuess) {
        this.message = "Congratulations, you guessed the number!";
      } else if (this.guess > this.numberToGuess) {
        this.message = "Too high. Try again.";
      } else {
        this.message = "Too low. Try again.";
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
