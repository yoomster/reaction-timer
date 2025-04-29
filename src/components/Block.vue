<template>
  <div class="block" @click.self="closeBlock">
    <h1>click me!</h1>
  </div>
</template>

<script>
export default {
  props: ["delay"],

  methods: {
    closeBlock() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.block {
  width: 400px;
  padding: 100px 0;
  margin: 40px auto;
  background: #0faf87;
  color: white;
  border-radius: 20px;
  text-align: center;
}
</style>
