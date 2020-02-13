<template>
  <div class="tj-col" :class="['tj-col-'+span,calcColGutter?'clear':'']" :style="calcColGutter">
    <slot></slot>
  </div>
</template>
<script>
export default {
  name: "TjCol",
  props: {
    span: {
      type: Number,
      default: 24
    }
  },
  computed: {
    calcColGutter() {
      if (this.$parent.gutter !== 0) {
        let value = +(this.$parent.gutter / 2) + "px";
        return {
          paddingLeft: value,
          paddingRight: value
        };
      }
      return "";
    }
  }
};
</script>

<style lang="scss">
.tj-col {
  // display: inline-block;
  float: left;
  box-sizing: border-box;
}

@for $item from 1 through 24 {
  .tj-col-#{$item} {
    width: 100%/24 * $item;
  }
}
// 处理gutter的左侧 右侧问题。 element 源码用margin 负数拉升,我使用css选择直接第一个最后一个
.tj-row {
  .tj-col.clear:first-child {
    padding-left: 0 !important;
  }
  .tj-col.clear:last-child {
    padding-right: 0 !important;
  }
}
</style>