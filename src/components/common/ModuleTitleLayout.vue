<template>
  <div class="title">
    <div class="left">
      <slot></slot>
    </div>
    <div class="right">
      <slot name="right"></slot>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="less" scoped>
.title {
  display: flex;
  justify-content: center;
  .left {
    display: flex;
    align-items: center;
  }
  .right {
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }
}
</style>
