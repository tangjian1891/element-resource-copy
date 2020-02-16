<template>
  <section class="tj-container" :class="{'is-vertical':isVertical}">
    <slot></slot>
  </section>
</template>

<script>
export default {
  props: {
    direction: String
  },

  computed: {
    isVertical() {
      // 如果是垂直 那么就是垂直
      if (this.direction === "vertical") {
        return true;
        // 如果不是就不是
      } else if (this.direction === "horizontal") {
        return false;
      }
      // 如果没有传递。那么久检测一下
      return this.$slots && this.$slots.default
        ? this.$slots.default.some(vnode => {
            const tag = vnode.componentOptions && vnode.componentOptions.tag;
            return tag === "tj-header" || tag === "tj-footer";
          })
        : false;
    }
  }
};
</script>

<style lang="scss">
.tj-container {
  display: flex;
  flex-direction: row;
  flex: 1;
  flex-basis: auto;
  box-sizing: border-box;
  min-width: 0;
}
.tj-container.is-vertical {
  flex-direction: column;
}
</style>