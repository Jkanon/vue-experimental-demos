<template>
  <div class="wrapper">
    <eyeball />
  </div>
</template>

<script>
import Eyeball from '@/components/Eyeball'

export default {
  name: 'FloatingEyeball',
  components: {
    Eyeball
  }
}
</script>

<style scoped>
.wrapper {
  width: 100%;
  height: 100%;
  min-height: 100vh;
  display: flex;
  flex-wrap: nowrap;
  flex-direction: column;
  align-items: center;;
  justify-content: center;
  background-image: radial-gradient(ellipse at 50% 0%, #eef 0, #888 100%);
}
</style>
