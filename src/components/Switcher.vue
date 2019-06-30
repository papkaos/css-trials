<template>
  <div class="switcher">
    <span>CSS Grid</span>
    <div
      class="switcher--toggle"
      @click="toggle"
      :class="{'is-active': !isCssGrid}"
    >
      <div class="switcher--ico"></div>
    </div>
    <span>Flexbox</span>
  </div>
</template>

<script>
  export default {
    name: "Switcher",
    props: ['isCssGrid'],
    methods: {
      toggle() {
        this.$emit('toggled', this.isCssGrid)
      }
    }
  }
</script>

<style lang="scss" scoped>
  .switcher {
    display: flex;
    align-items: center;
    font-size: 14px;
    z-index: 999;
  }

  .switcher--toggle {
    position: relative;
    width: 68px;
    height: 22px;
    margin-left: 15px;
    margin-right: 15px;
    background-color: #c5bdbb;
    border: 2px solid #110a0d;
    border-radius: 7px;

    &.is-active .switcher--ico {
      transform: translateX(42px);
    }
  }

  .switcher--ico {
    position: absolute;
    top: -4px;
    left: -2px;
    width: 30px;
    height: 30px;
    background-color: greenyellow;
    transition: transform 0.3s;
  }
</style>