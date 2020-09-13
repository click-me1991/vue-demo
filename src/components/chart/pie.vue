<template>
  <div class="pie"></div>
</template>

<script>
export default {
  name: "Pie"
};
</script>

<style scoped>
.pie {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  background: conic-gradient(
    deeppink 0 30%,
    yellowgreen 30% 70%,
    teal 70% 100%
  );
}
</style>
