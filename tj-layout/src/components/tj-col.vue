<template>
  <div class="tj-col" :class="['tj-col-'+span,'tj-col-offset-'+offset]" :style="[calcColGutter]">
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
    },
    offset: {
      type: Number,
      default: 0
    }
  },

  computed: {
    // 每个col左右padding
    calcColGutter() {
      if (this.$parent.gutter !== 0) {
        let value = +(this.$parent.gutter / 2) + "px";
        return {
          paddingLeft: value,
          paddingRight: value
        };
      }
      return "";
    },
    // 开始偏移
    calcColOffset() {
      // 偏移百分比。如果这个元素是第一个col，则取消左padding为0
      if (this.offset === 0) {
        return;
      }
      let value = (100 / 24) * this.offset + "%";
      return {
        marginLeft: value
      };
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

@for $item from 1 through 24 {
  .tj-col-offset-#{$item} {
    margin-left: 100%/24 * $item;
  }
}
// 处理gutter的左侧 右侧问题。 element 源码用margin 负数拉升,我使用css选择直接第一个最后一个
// .tj-row {
//   .tj-col.clear:first-child {
//     padding-left: 0;
//   }
//   .tj-col.clear:last-child {
//     padding-right: 0;
//   }
// }
</style>