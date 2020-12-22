<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResults" :score="score" />
</template>

<script>
  import Block from "./components/Block";
  import Results from "./components/Results";

  export default {
    name: "App",
    components: { Block, Results },
    data() {
      return {
        isPlaying: false,
        delay: null,
        score: null,
        showResults: false,
      };
    },
    methods: {
      start() {
        this.delay = 1000 + Math.random() * 6000;
        this.isPlaying = true;
        this.showResults = false;
      },
      endGame(reactionTime) {
        this.score = reactionTime;
        this.isPlaying = false;
        this.showResults = true;
      },
    },
  };
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #444;
    background: #cfcfcf;
    padding-top: 60px;
    height: 100vh;
  }
  button {
    text-transform: uppercase;
    background: #444;
    color: #fff;
    border: 1px solid #fff;
    height: 35px;
    width: 100px;
    font-size: 1.3rem;
  }
  button[disabled] {
    opacity: 0.7;
    background: #999;
    cursor: not-allowed;
  }
</style>
