<template>
  <el-card class="box-card">
    <div slot="header" class="clearfix">
      <span style="font-size: 32px;">index -- 索引</span>
    </div>
    <div class="text item">
      <router-link tag="li" to="/spacewaves">
        <a>Space Waves Effects implements by ThreeJS——空间粒子波浪特效</a>
      </router-link>
      <router-link tag="li" to="/sidebar">
        <a>Sidebar With Dynamic Background-Image——随机背景侧边栏</a>
      </router-link>
    </div>
  </el-card>
</template>

<script>
export default {
  name: 'Index'
}
</script>

<style scoped>
a {
  color: #409eff;
}
a:hover {
  color: #66b1ff;
}

.item li:not(:last-child) {
  margin-bottom: 10px;
}
</style>
