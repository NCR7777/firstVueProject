<template>
  <div class="header">
    <div class="header-left">
      <router-link to="">
        <div class="iconfont back-icon">&#xe658;</div>
      </router-link>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe63c;</span>输入城市/景点/游玩主题</div>
    <router-link to="/city">
      <div class="header-right">
        <div class="city">{{this.$store.state.city}}</div><span class="iconfont icon-arrow">&#xe65c;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .header
    display: flex
    line-height: $headerHeight
    background: $bgColor
    color: #fff
    .header-left
      float: left
      width: .7rem
      .back-icon
        color #fff
        padding-left:.1rem
        text-align: center
        font-size: .6rem
    .header-input
      flex: 1
      height: .60rem
      line-height: .60rem
      margin-top: .12rem
      margin-left: .2rem
      padding-left: .2rem
      background: #fff
      border-radius: .1rem
      color: #999
    .header-right
      display flex
      justify-content center
      float: right
      width: 1.24rem
      height $headerHeight
      text-align: center
      color #fff
      .city
        ellipsis()
      .icon-arrow
        font-size: .32rem
</style>
