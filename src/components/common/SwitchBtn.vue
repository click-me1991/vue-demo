<template>
  <div class="switch-btn">
    <div
      class="item"
      :class="[item.value === localValue ? 'active' : '']"
      :key="idx"
      v-for="(item, idx) in list"
      @click="clickEvt(item.value)"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script>
export default {
  name: "SwitchBtn",
  props: {
    value: {
      type: Number,
      default: 0
    },
    list: {
      type: Array,
      default: function() {
        return [
          {
            name: "小学",
            value: 0
          },
          {
            name: "中学",
            value: 1
          }
        ];
      }
    }
  },
  data() {
    return {
      localValue: 0
    };
  },
  methods: {
    clickEvt(value) {
      this.localValue = value;
      this.$emit("switch", this.localValue);
    }
  },
  mounted() {
    this.localValue = this.value;
  }
};
</script>

<style lang="less">
.switch-btn {
  display: flex;
  width: 1.8rem;
  height: 0.4rem;
  border-radius: 0.4rem;
  overflow: hidden;
  color: #fff;
  background-color: #0f4588;
  cursor: pointer;
  .item {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 0.4rem;
    height: 100%;
    &.active {
      background-color: #186ef2;
    }
  }
}
</style>
