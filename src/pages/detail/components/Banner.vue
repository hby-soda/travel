<template>
    <div>
      <div class="banner" @click="handleBannerClick">
        <img
          class="banner-img"
          :src="SightImg"/>
        <div class="banner-info">
          <div class="banner-title">{{this.SightName}}</div>
        </div>
        <div class="banner-num">
          <span class="iconfont banner-icon">&#xe626;</span>
          {{this.GallaryImg.length}}
        </div>
      </div>
      <common-gallary :imgs="GallaryImg" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  props: {
    SightName: String,
    SightImg: String,
    GallaryImg: Array
  },
  data () {
    return {
      showGallary: false
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
