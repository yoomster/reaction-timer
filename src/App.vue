<template>
  <h1>Think your fast?</h1>
  <p>Test it with this reaction timer</p>
  <button @click="toggleBlock">click to start</button>
  <div v-if="showBlock">
    <Block></Block>
  </div>
</template>

<script>
import Block from "./components/Block.vue";

export default {
  name: "App",
  components: { Block },
  methods: {
    toggleBlock() {
      this.showBlock = !this.showBlock;
    },
  },
  data() {
    return {
      showBlock: false,
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
