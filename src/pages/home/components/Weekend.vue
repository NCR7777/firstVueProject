<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of weekendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" :alt="item.title">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
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
      weekendList: [{
        id: '0001',
        imgUrl: '/static/index-recommend/weekend/weekend1.jpg',
        title: '深圳周边游',
        desc: '远离城市拥堵，去周边开启清新假期吧。'
      }, {
        id: '0002',
        imgUrl: '/static/index-recommend/weekend/weekend2.jpg',
        title: '清远周边逛',
        desc: '人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'
      }, {
        id: '0003',
        imgUrl: '/static/index-recommend/weekend/weekend3.jpg',
        title: '浮在海上的绿洲',
        desc: '南国滨海之城，避寒胜地，有暖暖的阳光，海风习习，吃着海鲜逛逛老街多惬意啊！'
      }]
    }
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
  .item-img-wrapper
    overflow hidden
    height 0
    padding-bottom 36.8%
    .item-img
      width 100%
  .item-info
    flex 1
    padding .14rem .2rem .2rem .2rem
    min-width 0
    .item-title
      padding-right: 1.4rem
      line-height .48rem
      font-size .28rem
      color $darkTextColor
      ellipsis()
    .item-desc
      padding-right: 1rem
      font-size .24rem
      line-height .42rem
      color $grayTextColor
      ellipsis()
</style>
