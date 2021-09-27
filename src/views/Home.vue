<template>
  <div class="home">
    <input v-model="inputValue" />
    <h3>{{ inputValue }}</h3>
    <button @click="handleToSub">到详情页</button>
    <router-view @reload="handleReload" />
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      inputValue: "",
    };
  },
  methods: {
    handleToSub() {
      // 注意路由格式，是基于上一个路由/home下面的sub，不是独立的/sub
      this.$router.push("/home/sub");
    },

    handleReload(val) {
      // 这里可以做一些重新获取数据的操作，比如在详情页修改数据，返回后重新拉取列表
      console.log("reload", val);
    },
  },
  mounted() {
    // 子页面返回，不会重新跑生命周期
    console.log("主页面mounted");
  },
};
</script>

<style scoped>
.home {
  position: relative;
}
</style>
