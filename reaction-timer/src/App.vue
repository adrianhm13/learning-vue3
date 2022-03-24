<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <BlockContainer v-if="isPlaying" :delay="delay"/>
</template>

<script>
import BlockContainer from "./components/BlockContainer";

export default {
  name: "App",
  components: { BlockContainer },
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
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
  margin-top: 60px;
}
</style>
