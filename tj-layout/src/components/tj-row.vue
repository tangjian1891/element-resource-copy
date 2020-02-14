<template>
  <div :class="['tj-row',{'tj-row-flex':setflex}]" :style="[setJustify,calcRowGutter]">
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
    },
    type: {
      type: String,
      default: ""
    },
    justify: {
      type: String,
      default: ""
    }
  },
  computed: {
    setJustify() {
      if (this.justify === "") {
        return "";
      }
      return {
        "justify-content": this.justify
      };
    },
    setflex() {
      return this.type === "flex";
    },
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
    // 因为第一个元素的和最后一个元素的 内边距问题。
  }
};
</script>

<style lang="scss">
.tj-row-flex {
  display: flex;
  justify-content: flex-start;
}
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
  &-flex {
    display: flex;
  }
}
</style>