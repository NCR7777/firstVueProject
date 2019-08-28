<template>
  <div class="header">
    <router-link to="/">
      <div class="iconfont header-back">&#xe658;</div>
    </router-link>
      城市选择
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position relative
    overflow hidden
    line-height: $headerHeight
    text-align center
    color: #fff
    background: $bgColor
    font-size .32rem
    .header-back
      position absolute
      top 0
      left 0
      width .7rem
      font-size: .6rem
      color #fff
      padding-left:.05rem
</style>
