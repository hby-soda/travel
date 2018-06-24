<template>
    <div class="recommend">
      <div class="hr-10"></div>
      <div class="title">
        <img class="t-img" src="https://imgs.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="猜你喜欢"/>
        <span class="t-txt">猜你喜欢</span>
      </div>
      <ul class="list">
        <li
          class="item"
          v-for="item of list"
          :key="item.id"
        >
          <div class="item-img-wrapper">
            <img class="item-img" :src="item.imgurl"/>
          </div>
          <div
            class="tag"
            style="background-image: url(https://img1.qunarzz.com/piao/fusion/1802/20/2ba6d10b17972e02.png)"
            v-if="item.tag1"
          >
            随买随用
          </div>
          <div
            class="tag"
            style="background-image:url(https://img1.qunarzz.com/piao/fusion/1802/52/b9080e45b69b4f02.png)"
            v-if="item.tag2"
          >
            可订明日
          </div>
          <div v-else-if="!item.tag1"></div>
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-talk">查看{{item.talknum}}条评论</p>
            <p class="item-price">
              <span class="price">
                ¥
                <em class="price-num">{{item.pricenum}}</em>
              </span>
              起
              <span class="item-address">{{item.address}}</span>
            </p>
            <p class="item-desc">{{item.desc}}</p>
          </div>
        </li>
      </ul>
      <div class="btn">查看所有产品</div>
    </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      list: [{
        id: '0001',
        imgurl: 'https://imgs.qunarzz.com/sight/p0/1505/18/18ffcca94b1b7ca2.water.jpg_200x200_9b0d2dc4.jpg',
        tag1: true,
        tag2: false,
        title: '长恨歌',
        talknum: '9250',
        pricenum: '198',
        address: '',
        desc: '帅的人都去过了😎，你还等什么~'
      }, {
        id: '0002',
        imgurl: 'https://imgs.qunarzz.com/sight/p0/1602/de/de8400021b664c5390.img.jpg_200x200_46b16057.jpg',
        tag1: true,
        tag2: false,
        title: '华清宫（华清池·骊山）',
        talknum: '21797',
        pricenum: '135',
        address: '临潼区',
        desc: '览盛唐宫阙，登骊山怀古，赏长恨歌舞'
      }, {
        id: '0003',
        imgurl: 'https://imgs.qunarzz.com/sight/p0/1508/db/dbd0bef45fbc36b3.img.jpg_200x200_1b88abcf.jpg',
        tag1: false,
        tag2: true,
        title: '大唐芙蓉园',
        talknum: '18891',
        pricenum: '85',
        address: '曲江旅游...'
      }, {
        id: '0004',
        imgurl: 'https://imgs.qunarzz.com/sight/p0/1411/1a/5582f9f24bc50b475a8cbda4c5ac8d24.water.jpg_200x200_a0d48950.jpg',
        tag1: true,
        tag2: false,
        title: '秦始皇陵博物院（兵马俑）',
        talknum: '70345',
        pricenum: '267.8',
        address: '临潼区',
        desc: '世界第八大奇迹'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.recommend
  background #ffffff
  .hr-10
    height .2rem
    background #f2f2f2
  .title
    padding .24rem 0
    .t-img
      display inline-block
      overflow hidden
      width .3rem
      height .3rem
      margin-left .2rem
      vertical-align top
    .t-txt
      display inline-block
      margin-left .08rem
      height .44rem
      color #212121
      font-size .32rem
      line-height .44rem
  .list
    margin-left .24rem
    border-bottom .02rem solid #eee
    .item
      position relative
      overflow hidden
      padding .2rem 0
      .item-img-wrapper
        float left
        overflow hidden
        width 2rem
        height 2rem
        .item-img
          width 100%
      .tag
        position absolute
        top .2rem
        left 0
        width 1.02rem
        height .38rem
        background-size 100%
        color #fff
        font-size .2rem
        line-height .38rem
        text-indent .04rem
      .item-info
        overflow hidden
        padding-left .22rem
        .item-title
          margin-top .26rem
          height .44rem
          color #212121
          font-size .32rem
          line-height .44rem
          ellipsis()
        .item-talk
          margin-top: .14rem;
          height: .34rem;
          color: #616161;
          font-size: .24rem;
          line-height: .34rem;
          vertical-align: text-bottom;
        .item-price
          position relative
          margin-top .22rem
          color #616161
          font-size .24rem
          line-height .4rem
          .price
            color #ff8300
            .price-num
              font-size .4rem
          .item-address
            position: absolute;
            right: .24rem;
            bottom: 0;
        .item-desc
          display inline-block
          margin-top .48rem
          margin-right .24rem
          background #fff9f9
          padding .04rem .1rem
          color #f55
          font-size .24rem
          line-height .34rem
          ellipsis()
  .btn
    display block
    padding .2rem 0
    color #00afc7
    font-size .28rem
    line-height .4rem
    text-align center
</style>
