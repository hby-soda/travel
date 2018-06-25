<template>
    <div>
      <h2 class="title">周末去哪儿</h2>
      <ul>
        <li
          class="item"
          v-for="item of weekendList"
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
  props: {
    weekendList: Array
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
