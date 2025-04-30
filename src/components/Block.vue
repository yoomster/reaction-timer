<template>
  <div class="block" v-if="showBlock" @click="stopTimer">click me</div>
</template>

<script>
export default {
  props: ["delay"],

  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },

  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
  unmounted() {
    console.log("unmounted");
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      console.log(this.reactionTime);
    },
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
