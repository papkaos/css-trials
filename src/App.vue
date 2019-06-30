<template>
  <div id="app">
    <app-css-grid v-if="isCssGrid"></app-css-grid>
    <app-flexbox v-if="!isCssGrid"></app-flexbox>
    <app-switcher
      class="switcher-wrapper"
      :is-css-grid="isCssGrid"
      @toggled="onToggle"
    ></app-switcher>
  </div>
</template>

<script>
import CssGrid from "./components/CssGrid";
import Switcher from "./components/Switcher";
import FlexboxGrid from "./components/FlexboxGrid";

export default {
  name: 'app',
  data () {
    return {
      isCssGrid: true
    }
  },
  components: {
    'app-css-grid': CssGrid,
    'app-flexbox': FlexboxGrid,
    'app-switcher': Switcher
  },
  methods: {
    onToggle() {
      console.log('here');
      this.isCssGrid = !this.isCssGrid;
    }
  }
}
</script>

<style lang="scss" scoped>

  #app {
    min-height: inherit;
    height: 1px;
  }

  .switcher-wrapper {
    position: fixed;
    top: 20px;
    right: 20px;
  }
</style>
