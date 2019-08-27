<template>
  <div>
    <div class="title"><span class="iconfont guess-like">&#xe85c;</span>猜你喜欢</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
          <img class="item-img" :src="item.imgUrl" :alt="item.title">
        <div class="item-info">
            <p class="item-title">{{item.title}}</p>
          <div class="item-middle">
            <div class="item-star">
              <strong class="item-star-gain iconfont">&#xe626;&#xe626;&#xe626;&#xe626;&#xe626;</strong>
              <span class="item-star-total iconfont">&#xe626;&#xe626;&#xe626;&#xe626;&#xe626;</span>
            </div>
            <span class="item-desc">{{item.commitNum}}条评价</span>
          </div>
          <div class="item-bottom">
            <span class="item-price">¥<em class="item-price-num">{{item.price}}</em></span>起
            <span class="item-address">{{item.address}}</span>
          </div>

        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles"
  @import "~styles/mixins"
  .title
    margin-top .2rem
    line-height .8rem
    background rgb(245, 245, 245)
    text-indent .2rem
    .guess-like
      line-height .4rem
      color rgb(255, 91, 88)
      margin-left .1rem
      margin-right .1rem
  .item
    overflow hidden
    display flex
    height 2.4rem
    .item-img
      width 2rem
      height 2rem
      padding .2rem
    .item-info
      flex 1
      padding .1rem
      min-width 0
      .item-middle
        margin-top: .14rem
        height: .34rem
        .item-star
          display: inline-block
          position relative
          width: 1.7rem
          height: .28rem
          line-height: .28rem
          letter-spacing: .02rem
          .item-star-total
            overflow: hidden
            position: absolute
            top: .04rem
            left: 0
            height: .28rem
            font-size: .2rem
            z-index 1
            color #e0e0e0
          .item-star-gain
            overflow: hidden
            position: absolute
            top: .04rem
            left: 0
            height: .28rem
            font-size: .2rem
            color #ffb436
            z-index 2
        .item-desc
          font-size .24rem
          line-height .34rem
          color $grayTextColor
      .item-title
        margin-top .35rem
        height .44rem
        line-height .44rem
        font-size .32rem
        color $darkTextColor
        ellipsis()
    .item-bottom
      position: relative;
      margin-top: .22rem;
      color: $grayTextColor;
      font-size: .24rem;
      line-height: .4rem;
      .item-price
        color #ff8830
        .item-price-num
          font-size .4rem
      .item-address
        position: absolute;
        right: .24rem;
        bottom: 0;
</style>
