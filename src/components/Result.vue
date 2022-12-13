<template>
  <p>Reaction Time is {{ score }}ms</p>
  <p class="rank">{{ rank }}</p>
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
    this.score < 250
      ? (this.rank = "Ninja Fingers")
      : this.score < 400
      ? (this.rank = "Rapid Reflexes")
      : (this.rank = "Snail pace...");
  },
};
</script>
