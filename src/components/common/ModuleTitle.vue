<template>
  <div class="module-title">
    {{ title }}
  </div>
</template>

<script>
export default {
  name: "ModuleTitle",
  props: {
    title: {
      type: String,
      default: "任教学科分布"
    }
  }
};
</script>

<style lang="less" scoped>
.module-title {
  position: relative;
  display: flex;
  align-items: flex-end;
  justify-content: center;
  color: #fff;
  font-size: 0.2rem;
  font-weight: bolder;
  padding: 0 0.2rem;
  margin-left: 0.2rem;
  &:before {
    position: absolute;
    bottom: 0.02rem;
    content: "";
    display: inline-block;
    width: 100%;
    height: 0.2rem;
    border: 0.02rem solid #fff;
    border-top: none;
    border-bottom: none;
  }
  &:after {
    box-sizing: border-box;
    position: absolute;
    content: "";
    display: inline-block;
    width: calc(100% - 0.16rem);
    height: 0.1rem;
    bottom: 0.02rem;
    margin: 0 auto;
    border: 0.02rem solid #fff;
    border-top: none;
    border-bottom: none;
  }
}
</style>
