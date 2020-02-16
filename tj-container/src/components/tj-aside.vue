<!--
 * @Description: 
 * @Author: TangJian
 * @Date: 2020-02-16 10:24:06
 -->
<template>
  <aside class="tj-aside" :style="{ width }">
    <slot></slot>
  </aside>
</template>

<script>
export default {
  props: {
    width: {
      type: String,
      default: "300px"
    }
  }
};
</script>

<style lang="scss">
</style>