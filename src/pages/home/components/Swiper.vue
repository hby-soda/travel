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
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/98/0a2e0bd8eb0c0802.png_750x200_0a34d4a8.png'
      }, {
        id: '0002',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1806/56/d939255eab633a02.jpg_750x200_c08a2c07.jpg'
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
    padding-bottom 31.25%
    background #eee
    .swipe-img
      width 100%
</style>
