<template lang="pug">
  el-row
    el-col.desktop-col.hidden-xs-only(:sm="8")
      p MENÚ SIMULADO
    el-col.hidden-sm-and-up
      include ../assets/icons/menu-filled.svg
    el-col(:xs="24" ,:sm="{ span: 16, offset: 8 }")
      main-carousel
    el-col(:xs="24" ,:sm="{ span: 16, offset: 8 }")
      articles-list
</template>

<script>
import MainCarousel from '@/components/Carousel'
import ArticlesList from '@/components/Articles'
export default {
  name: 'MainContent',
  components: {
    MainCarousel,
    ArticlesList
  }
}
</script>

<style lang="scss">
  .desktop-col {
    position: absolute;
  }
</style>
