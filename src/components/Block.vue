<template>
  <div class="block" v-if="showBlock">
    Click Me
  </div>
</template>

<script>
export default {
  props: ['delay'],
  data() {
    return {
      showBlock: false
    }
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true
    }, this.delay)
  }
}
</script>

<style>
  .block {
    width: 400px;
    border-radius: 5px;
    background: #0faf87;
    color: #fff;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    text-transform: uppercase;
    font-size: 2.2rem;
  }
</style>