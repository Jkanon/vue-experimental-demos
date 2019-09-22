<template>
  <section class="app-main">
    <transition name="fade-transform" mode="out-in">
      <el-scrollbar style="height: 100%;">
        <keep-alive :include="cachedViews">
          <router-view :key="key" />
        </keep-alive>
      </el-scrollbar>
    </transition>
  </section>
</template>

<script>
export default {
  name: 'AppMain',
  computed: {
    cachedViews() {
      return this.$store.state.tagsView.cachedViews
    },
    key() {
      return this.$route.path
    }
  }
}
</script>

<style lang="scss" scoped>
.app-main {
  /*50 = navbar  */
  height: 100vh;
  width: 100%;
  position: relative;
  overflow: hidden;
}
.fixed-header+.app-main {
  padding-top: 50px;
}

.hasTagsView {
  .fixed-header+.app-main {
    padding-top: 84px;
  }
}
</style>
