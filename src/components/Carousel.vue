<template lang="pug">
  el-carousel(:autoplay="false" )
    el-carousel-item(v-for="item in 3" ,:key="item")
      h3 {{ item }}
</template>
<script>

export default {
  name: 'MainCarousel',
  data() {
    return {}
  }
}
</script>
<style lang="scss">
  .el-carousel__item {
    &:nth-child(2n) {
      background: {
        color: #99a9bf;
      }
    }
    &:nth-child(2n+1) {
      background: {
        color: #d3dce6;
      }
    }
    h3 {
      text: {
        align: center;
      }
    }
  }
</style>