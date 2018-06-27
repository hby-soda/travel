<template>
    <div>
      <div class="banner" @click="handleBannerClick">
        <img
          class="banner-img"
          src="https://img1.qunarzz.com/sight/p0/1505/18/18ffcca94b1b7ca2.water.jpg_600x330_cd78f1b7.jpg"/>
        <div class="banner-info">
          <div class="banner-title">长恨歌</div>
        </div>
        <div class="banner-num">
          <span class="iconfont banner-icon">&#xe626;</span>
          34
        </div>
      </div>
      <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      showGallary: false,
      imgs: ['https://img1.qunarzz.com/sight/p0/1505/18/18ffcca94b1b7ca2.water.jpg_600x330_cd78f1b7.jpg',
        'http://img1.qunarzz.com/sight/p0/1706/73/7349ea5c85af9d5ea3.img.png_r_800x800_2afd15e0.png']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    overflow hidden
    height 0
    padding-bottom 55%
    .banner-img
      width 100%
    .banner-info
      position absolute
      right 0
      bottom 0
      left 0
      min-height .4rem
      padding .2rem
      background-image linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.7))
      .banner-title
        position: relative;
        z-index: 1;
        line-height: .4rem;
        color: #fff;
        font-size: .36rem;
        text-shadow: 0 1px 2px rgba(0,0,0,0.70);
    .banner-num
      position absolute
      left .2rem
      bottom .86rem
      width 1.2rem
      height .4rem
      background rgba(0,0,0,.5)
      border-radius .2rem
      font-size .24rem
      color #fff
      line-height .4rem
      text-align center
      .banner-icon
        position relative
        top .02rem
</style>
