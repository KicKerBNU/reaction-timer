<template>
  <div class="container">
    <h1> Reaction Timer </h1>
    <button @click="start" :disabled="isPlaying">Play </button>
    <Block v-if="isPlaying" :delay="delay" @end="endGame" />
    <div class="space"></div>
    <Results v-if="showResults" :score="score" />
  </div>
</template>

<script>
import Block from "./components/Block.vue"
import Results from "./components/Results.vue";
export default {
  name: 'App',
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResults = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    }
  }
}
</script>

<style>

</style>