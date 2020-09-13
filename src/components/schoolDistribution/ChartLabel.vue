<template>
  <div class="chart-label">
    <div class="item" :key="index" v-for="(item, index) in labelList">
      <span class="icon" :style="{ backgroundColor: colors[index] }"></span>
      <span class="text">{{ item }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    labelList: {
      type: Array,
      default: function() {
        return ["民办", "私立", "公办"];
      }
    },
    colors: {
      type: Array,
      default: function() {
        return ["#00FCFF", "#00C646", "#125BE1"];
      }
    }
  }
};
</script>

<style lang="less" scoped>
.chart-label {
  display: flex;
  .item {
    display: flex;
    align-items: center;
    flex-flow: row;
    color: #fff;
    margin-left: 0.2rem;
    .icon {
      display: inline-block;
      width: 0.1rem;
      height: 0.06rem;
      border-radius: 0.03rem;
      background-color: #f00;
      margin-right: 0.08rem;
    }
  }
}
</style>
