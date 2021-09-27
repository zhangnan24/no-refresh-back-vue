<template>
  <div class="sub">
    <h1>这是详情页</h1>
    <button @click="() => $router.back()">router.back</button>
  </div>
</template>

<script>
export default {
  beforeDestroy() {
    // 可以传自定义参数，如果没需要，也可以不做
    this.$emit("reload", "局部更新，比如根据当前搜索条件搜索下列表");
  },
};
</script>

<style scoped>
.sub {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: #fff;
}
</style>
