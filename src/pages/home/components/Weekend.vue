<template>
    <div>
      <h2 class="title">周末去哪儿</h2>
      <ul>
        <li
          class="item"
          v-for="item of list"
          :key="item.id"
        >
          <div class="item-img">
            <img
              class="img"
              :src="item.imgurl"
            />
          </div>
          <div class="item-info">
            <p class="name">{{item.name}}</p>
            <p class="desc">{{item.desc}}</p>
          </div>
        </li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      list: [{
        id: '0001',
        imgurl: 'https://imgs.qunarzz.com/sight/source/1505/19/58f233e11df7ef.jpg_r_640x214_6b42c9fc.jpg',
        name: '西安必游TOP10',
        desc: '寻长安梦，开启穿越的圆梦之旅'
      }, {
        id: '0002',
        imgurl: 'https://imgs.qunarzz.com/sight/source/1511/14/1cf5dc2ecbfc16.jpg_r_640x214_b4b3a58a.jpg',
        name: '最美丝路行',
        desc: '情系西北，中国梦丝路行'
      }, {
        id: '0003',
        imgurl: 'https://imgs.qunarzz.com/sight/source/1507/fe/679926851c309a.jpg_r_640x214_114816de.jpg',
        name: '不一样的周末',
        desc: '这个周末玩点不一样的'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
  height .8rem
  padding-left .26rem
  line-height .8rem
  color #212121
  background #eee
.item-img
  overflow hidden
  height 0
  padding-bottom 37.4375%
  .img
    width 100%
.item-info
  position relative
  padding .14rem .2rem .2rem .2rem
  .name
    padding-right 1.4rem
    color #212121
    font-siz: .28rem
    line-height .48rem
    ellipsis()
  .desc
    padding-right 1.4rem
    color #616161
    font-size .24rem
    line-height .42rem
    ellipsis()
</style>
