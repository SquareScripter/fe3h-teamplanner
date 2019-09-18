<template>
  <div class="unit-display">
    <h1 v-if="unit">{{unit.Name}}</h1>
    <h1 v-else>UNDEFINED</h1>
    <div id="stats-grid">
      <div>Lv 1</div>
      <StatDisplay key="hp" :unit="unit" stat="HP"/>
      <StatDisplay key="str" :unit="unit" stat="STR"/>
      <StatDisplay key="mag" :unit="unit" stat="Mag"/>
      <StatDisplay key="dex" :unit="unit" stat="Dex"/>
      <StatDisplay key="spd" :unit="unit" stat="Spd"/>
      <StatDisplay key="lck" :unit="unit" stat="Lck"/>
      <StatDisplay key="def" :unit="unit" stat="Def"/>
      <StatDisplay key="res" :unit="unit" stat="Res"/>
      <StatDisplay key="chm" :unit="unit" stat="Chm"/>
    </div>
  </div>
</template>

<script>
import StatDisplay from "./StatDisplay";

export default {
  name: "UnitDisplay",
  components: {
    StatDisplay
  },
  props: { unit: Object }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#stats-grid {
  display: grid;
  grid-template-columns: auto auto;
  grid-template-rows: auto auto auto auto auto;
}
</style>
