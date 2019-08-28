<template>
  <div>
    <div class="header border-bottom">
      <router-link to="/">
        <div class="iconfont header-back">&#xe658;</div>
      </router-link>
      城市选择
    </div>
    <div class="city-address">
      <ul class="address-ul border">
        <li class="address-item active border">境内</li>
        <li class="address-item border">境外·港澳台</li>
      </ul>
    </div>
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
  .city-address
    line-height $headerHeight
    background $bgColor
    padding .2rem 1rem
    color #fff
    .address-ul
      overflow: hidden
      border-radius .03rem
      height .4rem
      line-height .4rem
    .address-item
        width 50%
        float left
        height .4rem
        text-align center
    .active
      background #fff
      color $bgColor
</style>
