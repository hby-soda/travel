<template>
    <div>
      <detail-banner
        :SightName="SightName"
        :SightImg="SightImg"
        :GallaryImg="GallaryImg"
      ></detail-banner>
      <detail-header></detail-header>
      <div class="content">
        <detail-list :list="list"></detail-list>
      </div>
    </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailList,
    DetailHeader,
    DetailBanner
  },
  data () {
    return {
      SightName: '',
      SightImg: '',
      GallaryImg: [],
      list: []
    }
  },
  mounted () {
    this.getDetailInfo()
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      })
        .then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.SightName = data.SightName
        this.SightImg = data.SightImg
        this.GallaryImg = data.GallaryImg
        this.list = data.list
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.content
  height 50rem
</style>
