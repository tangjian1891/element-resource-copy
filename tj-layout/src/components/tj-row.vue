<template>
  <div class="tj-row">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "TjRow",
  props: {
    gutter: {
      type: Number,
      default: 0
    }
  },
  computed: {
    calcRowGutter() {
      if (this.gutter === 0) {
        return;
      }
      let value = "-" + (this.gutter / 2 + "px");
      return {
        marginLeft: value,
        marginRight: value
      };
    }
  }
};
</script>

<style lang="scss">
.tj-row {
  // box-sizing: border-box;
  &::after {
    content: "";
    display: block;
    clear: both;
  }
  &::before {
    content: "";
    display: block;
    clear: both;
  }
}
</style>