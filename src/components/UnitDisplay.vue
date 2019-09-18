<template>
  <div class="unit-display">
    <h1 v-if="unit">{{unit.Name}}</h1>
    <h1 v-else>UNDEFINED</h1>
  </div>
</template>

<script>
export default {
  name: "UnitDisplay",
  props: { unit: Object }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
