<!--
 * @Description: 
 * @Author: TangJian
 * @Date: 2020-02-16 10:23:57
 -->
<template>
  <main class="tj-main">
    <slot></slot>
  </main>
</template>

<script>
export default {};
</script>

<style class="scss">
.tj-main {
  display: block;
  flex: 1;
  flex-basis: auto;
  padding: 20px;
}
</style>