<template>
  <swiper class="wrapper" :options="swiperOption">
    <swiper-slide v-for="item of swiperList" :key="item.id">
      <img class="swipe-img" :src="item.imgUrl">
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    swiperList: Array
  },
  data () {
    return {
      swiperOption: {
        loop: true,
        autoplay: 2500,
        autoplayDisableOnInteraction: false,
        speed: 500,
        pagination: '.swiper-pagination'
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background #ffffff
  .wrapper
    width 100%
    height 0
    padding-bottom 26.67%
    background #eee
    .swipe-img
      width 100%
</style>
