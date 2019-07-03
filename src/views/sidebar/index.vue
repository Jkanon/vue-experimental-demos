<template>
  <div style="text-align: center; font-size: 30px;">
    请<a href="javascript:;" @click="refresh">刷新</a>页面查看效果
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'SideWithDynamicBG',
  computed: {
    ...mapGetters([
      'sidebar'
    ])
  },
  mounted() {
    if (!this.sidebar.opened) {
      this.$store.dispatch('app/toggleSideBar')
    }
  },
  methods: {
    refresh() {
      window.location.reload()
    }
  }
}
</script>

<style scoped>
  a {
    color: #409eff;
  }
  a:hover {
    color: #66b1ff;
  }
</style>
