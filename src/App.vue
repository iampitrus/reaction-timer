<!-- The program randomly delays the loading of the block to check how fast you are to click it anytime it appears on your screen. -->

<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <p v-if="showResult">Reaction time: {{ score }} ms</p>
</template>

<script>
import Block from "./components/Block.vue";
export default {
  name: "App",
  components: { Block },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResult = true;
    },
  },
};
</script>

<style>
#app {
  text-align: center;
}
</style>
