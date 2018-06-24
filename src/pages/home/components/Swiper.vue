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
  data () {
    return {
      swiperOption: {
        loop: true,
        autoplay: 2500,
        autoplayDisableOnInteraction: false,
        speed: 500,
        pagination: '.swiper-pagination'
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1806/fc/e47aa3e1c67bbc02.jpg_750x200_0f3eecf8.jpg'
      }, {
        id: '0002',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1806/64/cc63aa526e8bb302.png_750x200_d32776c5.png'
      }]
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
