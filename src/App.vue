<template>
  <h1>Reaction timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Results v-if="!isPlaying && score > 0" :score="score" />
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
</template>

<script>
import Block from "./components/Block.vue"
import Results from "./components/Results.vue"

export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: 0,
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    },
    endGame(ev) {
      this.score = ev
      this.isPlaying = false
    },
  },
  components: {
    Block,
    Results,
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
button {
    background: #0faf87;
    color: white;
    border: none;
    padding: 8px 16px;
    border-radius: 20px;
    font-size: 16px;
    letter-spacing: 1px;
    cursor: pointer;
    margin: 10px;
}

button[disabled] {
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
