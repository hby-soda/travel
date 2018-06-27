<template>
    <div>
      <home-header></home-header>
      <home-swiper :swiperList="swiperList"></home-swiper>
      <home-icons :iconList="iconList"></home-icons>
      <home-recommend :recommendList="recommendlist"></home-recommend>
      <home-weekend :weekendList="weekendlist"></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeWeekend,
    HomeRecommend,
    HomeIcons,
    HomeSwiper,
    HomeHeader
  },
  data () {
    return {
      swiperList: [],
      iconList: [],
      recommendlist: [],
      weekendlist: []
    }
  },
  mounted () {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendlist = data.recommendlist
        this.weekendlist = data.weekendlist
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
</style>
