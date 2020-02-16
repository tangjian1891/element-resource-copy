<template>
  <footer class="tj-footer" :style="{ height }">
    <slot></slot>
  </footer>
</template>

<script>
export default {
  props: {
    height: {
      type: String,
      default: "60px"
    }
  }
};
</script>

<style lang="scss">
.tj-footer {
  padding: 0 20px;
  flex-shrink: 0;
  box-sizing: border-box;
}
</style>