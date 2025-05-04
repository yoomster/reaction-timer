<template>
  <p>Reaction time: {{ speed }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ["speed"],

  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.speed < 250) this.rank = "Ninja finger";
    else if (this.speed < 400) this.rank = "that's an ok finger";
    else this.rank = "snail finger...";
  },

  methods: {},
};
</script>

<style>
.rank {
  font-size: 1.4em;
  color: #0faf87;
  font-weight: bold;
}
</style>
