<template>
  <p>Reaction Time - {{ score }} ms</p>
  <p class="rank">Rank: {{ rank }}</p>
</template>

<script>
  export default {
    props: ["score"],
    data() {
      return {
        rank: null,
      };
    },
    mounted() {
      if (this.score < 300) {
        this.rank = "Ninja";
      } else if (this.score < 400) {
        this.rank = "Cheetah";
      } else if (this.score < 450) {
        this.rank = "Gazelle";
      } else {
        this.rank = "Snail";
      }
    },
  };
</script>

<style>
  .rank {
    font-size: 1.4em;
    color: #822;
    font-weight: bold;
  }
</style>
