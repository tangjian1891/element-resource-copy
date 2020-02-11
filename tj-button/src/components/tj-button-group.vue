<template>
  <div class="tj-button-group">
    <slot></slot>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
.tj-button-group {
  .tj-button + .tj-button {
    margin-left: 0 !important;
  }
  .tj-button {
    border-radius: 0;
    &:first-child {
      border-top-left-radius: 4px;
      border-bottom-left-radius: 4px;
      border-width: 1px;
      border-right-color: hsla(0, 0%, 100%, 0.5);
    }
    &:last-child {
      border-width: 1px;
      border-left-color: hsla(0, 0%, 100%, 0.5);
      border-top-right-radius: 4px;
      border-bottom-right-radius: 4px;
    }
  }
}
</style>
