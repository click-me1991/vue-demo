<template>
  <div class="module">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Module"
};
</script>

<style lang="less">
.module {
  position: relative;
  width: 6.13rem;
  height: 3.03rem;
  border: 1px solid #ccc;
  padding: 0.2rem 0.3rem;
  background-color: rgba(0, 0, 0, 0.2);
}
</style>
