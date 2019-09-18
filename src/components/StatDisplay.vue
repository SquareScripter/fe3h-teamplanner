<template>
  <div class="unit-display">
    <div key="stats-grid" v-if="unit">
      <div key="stat">{{stat}} : {{statValue}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "StatDisplay",
  props: { unit: Object, stat: String },
  computed: {
    statValue: function() {
      return this.unit[this.stat];
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
