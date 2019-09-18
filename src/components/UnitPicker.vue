<template>
  <div id="unit-picker">
    <select
      id="select"
      :value="currentOption"
      @input="$emit('input',units[$event.target.selectedIndex - 1])"
    >
      <option disabled>Choose a unit</option>
      <option v-for="unit in units" v-bind:value="unit.Name" v-bind:key="unit.Name">{{ unit.Name }}</option>
    </select>
  </div>
</template>

<script>
import { UNITS } from "../data/units.js";

export default {
  name: "UnitPicker",
  props: {
    value: Object,
    units: {
      type: Array,
      // Object or array defaults must be returned from
      // a factory function
      default: function() {
        return UNITS;
      }
    }
  },
  data() {
    return {
      currentOption: null
    };
  },
  watch: {
    value: function(newValue) {
      this.currentOption = newValue;
    }
  }
};
</script>

<style>
</style>
