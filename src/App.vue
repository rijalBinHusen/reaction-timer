<template>
  <h1>Reaction timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <p v-if="!isPlaying">Reaction time: {{ score }}</p>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
</template>

<script>
import Block from "./components/Block.vue"

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
</style>
