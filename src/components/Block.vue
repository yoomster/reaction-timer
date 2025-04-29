<template>
  <div class="block" v-if="showBlock">click me</div>
</template>

<script>
export default {
  props: ["delay"],

  data() {
    return {
      showBlock: false,
    };
  },

  mounted() {
    setTimeout(() => {
      this.showBlock = true;
    }, this.delay);
  },
  unmounted() {
    console.log("unmounted");
  },
};
</script>

<style>
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
