<template>
    <div class="recommend">
      <div class="hr-10"></div>
      <div class="title">
        <img class="t-img" src="https://imgs.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="猜你喜欢"/>
        <span class="t-txt">猜你喜欢</span>
      </div>
      <div class="border-bottom">
        <ul class="list">
          <router-link
            tag="li"
            class="item"
            v-for="item of recommendList"
            :key="item.id"
            :to="'/detail/' + item.id"
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
          </router-link>
        </ul>
      </div>
      <div class="btn">查看所有产品</div>
    </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
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
  .border-bottom
    &:before
      border-color #ccc
    &:after
      border-color #ccc
    .list
      margin-left .24rem
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
