<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    <!--<HelloWorld msg="Hello Vue in CodeSandbox!"/>-->
    <UnitPicker :units="unitList" @input="selectedUnit = $event"/>
    <UnitDisplay :unit="selectedUnit"/>
  </div>
</template>

<script>
import { UNITS } from "./data/units.js";
//import HelloWorld from "./components/HelloWorld";
import UnitPicker from "./components/UnitPicker";
import UnitDisplay from "./components/UnitDisplay";

export default {
  name: "App",
  components: {
    //HelloWorld
    UnitPicker,
    UnitDisplay
  },
  data: function() {
    return {
      selectedUnit: null,
      unitList: UNITS
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
