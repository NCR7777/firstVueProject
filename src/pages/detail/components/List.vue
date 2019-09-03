<template>
    <div>
      <div class="item" v-for="(item, index) of this.categoryList" :key="index">
        <div class="item-title border-bottom">
          <span class="iconfont item-title-icon">&#xe602;</span>
          {{item.title}}
        </div>
        <div v-if="item.children" class="item-children">
          <detail-list :categoryList="item.children"></detail-list>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    categoryList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .item-title
    line-height .8rem
    font-size .32rem
    padding 0 .2rem
    .item-title-icon
      position relative
      left .06rem
      top 0
      display inline-block
      width .36rem
      height .36rem
      margin-right .1rem
      color $bgColor
  .item-children
    padding 0 .2rem
</style>
