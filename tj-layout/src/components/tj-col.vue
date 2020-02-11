<template>
  <div class="tj-col" :class="['tj-col-'+span]">
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
  }
};
</script>

<style lang="scss">
.tj-col {
  display: inline-block;
  border: 1px solid red;
  box-sizing: border-box;
}

@for $item from 1 through 24 {
  .tj-col-#{$item} {
    width: 100%/24 * $item;
  }
}
</style>