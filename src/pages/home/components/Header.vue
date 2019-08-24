<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe658;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe63c;</span>输入城市/景点/游玩主题</div>
    <div class="header-right icon-arrow">
    城市<span class="iconfont">&#xe65c;</span></div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display: flex
    line-height: .86rem
    background: $bgColor
    color: #fff
    .header-left
      float: left
      width: .7rem
      .back-icon
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
      float: right
      width: 1.24rem
      text-align: center
      .icon-arrow
        font-size: 1.2em
</style>
