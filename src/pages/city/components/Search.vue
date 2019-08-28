<template>
    <div class="search">
      <label for="search-input"></label>
      <input type="text" id="search-input" placeholder="输入城市名或拼音" class="search-input bottom" />
    </div>
</template>

<script>
export default {
  name: 'Search'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    height .56rem
    padding .03rem 1.5rem
    background $bgColor
    .search-input
      box-sizing border-box
      padding 0 .1rem
      width 100%
      height .5rem
      line-height .5rem
      text-align center
      border-radius .06rem
      color #666
</style>
