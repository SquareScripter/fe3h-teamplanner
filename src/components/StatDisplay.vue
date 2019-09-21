<template>
  <div :class="darkStyle?'stat-display-d':'stat-display'" style="width:14em; height:1.2em;">
    <div key="stats-grid">
      <div class="stat-name">{{stat}}</div>
      <div class="stat-value" v-if="statBar">{{statValue}}</div>
      <div class="stat-value" style="width: 85%; text-align: center" v-else>{{statValue}}</div>
      <div class="bar-bg" v-if="statBar">
        <div class="bar-fg" :style="{width: statValue*2+'%'}"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "StatDisplay",
  props: { unit: Object, stat: String, statBar: Boolean, darkStyle: Boolean },
  computed: {
    statValue: function() {
      if (this.unit) return this.unit[this.stat];
      else return 0;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.stat-display {
  margin: 2px;
  border-bottom: solid;
  border-width: 1px;
  border-color: rgba(0, 0, 0, 0.5);
  padding: 2px;
}
.stat-display-d {
  margin: 2px;
  border: solid;
  border-width: 2px;
  border-color: rgb(80, 75, 60);
  padding: 2px;
}
.stat-display-d > div {
  color: white;
  height: 1em;
  padding: 2px;
  background: rgb(80, 75, 60);
}
.stat-name {
  float: left;
  text-align: left;
  width: 2em;
}
.stat-value {
  float: right;
  text-align: right;
  width: 1em;
  font-weight: bold;
}
.bar-bg {
  width: 6em;
  background: rgba(0, 0, 0, 0.25);
  border-style: solid;
  border-width: 1px;
  border-color: rgba(0, 0, 0, 0.25);
  display: inline-block;
}
.bar-fg {
  height: 10px;
  background-image: linear-gradient(
    to right,
    rgb(185, 185, 250),
    rgb(200, 175, 250)
  );
}
</style>
