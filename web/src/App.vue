<template>
  <div id="app">
    <keep-alive><router-view></router-view></keep-alive>
    <div class="loding" v-if="$store.getters.globalLoading">
      <a-spin />
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  beforeCreate() {
    this.$store.dispatch('setGlobalLoading', false)
  },
}
</script>

<style scoped lang="less">
.router-view {
  height: 100vh;
}
.loding {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, .1);
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
