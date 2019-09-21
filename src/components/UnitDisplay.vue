<template>
  <div class="unit-display">
    <h1 v-if="unit">{{unit.Name}}</h1>
    <h1 v-else>UNDEFINED</h1>
    <div id="stats-grid">
      <StatDisplay key="lv" :unit="unit" stat="Lv"/>
      <div/>
      <StatDisplay key="hp" :unit="unit" stat="HP" darkStyle/>
      <StatDisplay key="mv" :unit="unit" stat="Mv"/>
      <StatDisplay key="str" :unit="unit" stat="STR" statBar/>
      <StatDisplay key="mag" :unit="unit" stat="Mag" statBar/>
      <StatDisplay key="dex" :unit="unit" stat="Dex" statBar/>
      <StatDisplay key="spd" :unit="unit" stat="Spd" statBar/>
      <StatDisplay key="lck" :unit="unit" stat="Lck" statBar/>
      <StatDisplay key="def" :unit="unit" stat="Def" statBar/>
      <StatDisplay key="res" :unit="unit" stat="Res" statBar/>
      <StatDisplay key="chm" :unit="unit" stat="Chm" statBar/>
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
  grid-template-columns: 16em 16em;
  grid-template-rows: auto auto auto auto auto;
}
</style>
