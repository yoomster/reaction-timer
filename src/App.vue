<template>
  <h1>Think your fast?</h1>
  <p>Test it with this reaction timer</p>
  <button @click="start" :disabled="isPlaying">click to play</button>
  <Block v-if="isPlaying" :delay="delay" @close="toggleBlock"></Block>
</template>

<script>
import Block from "./components/Block.vue";

export default {
  name: "App",
  components: { Block },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      console.log(this.delay);
    },
    toggleBlock() {
      this.showBlock = !this.showBlock;
    },
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
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
