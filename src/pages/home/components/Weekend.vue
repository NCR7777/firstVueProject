<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
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
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles"
  @import "~styles/mixins"
  .title
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
