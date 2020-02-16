<!--
 * @Description: 
 * @Author: TangJian
 * @Date: 2020-02-16 10:23:57
 -->
<template>
  <header class="tj-header" :style="{height}">
    <slot></slot>
  </header>
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
.tj-header {
  padding: 0 20px;
}
</style>