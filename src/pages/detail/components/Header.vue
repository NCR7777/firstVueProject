<template>
    <div>
      <router-link tag="div" to="/" class="header-abs" v-show="showAbsHeader">
        <span class="iconfont header-abs-back">&#xe658;</span>
      </router-link>
      <div class="header-fixed" v-show="showFixedHeader" :style="opacityStyle">
        <router-link tag="span" to="/" class="iconfont header-fixed-back">&#xe658;</router-link>
        世界之窗
      </div>
    </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbsHeader: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    showFixedHeader () {
      return !this.showAbsHeader
    },
    handleScroll () {
      const scrollTop = document.documentElement.scrollTop
      let opacity = 0
      if (scrollTop > 50) {
        opacity = opacity > 1 ? 1 : (scrollTop - 50) / 60
        this.showAbsHeader = false
      } else {
        this.showAbsHeader = true
      }
      this.opacityStyle = { opacity }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
  .header-abs
    position absolute
    left .2rem
    top .2rem
    width .8rem
    height .8rem
    border-radius .4rem
    text-align center
    line-height .8rem
    background rgba(0, 0, 0, .8)
    .header-abs-back
      font-size .6rem
      color rgba(255, 255, 255, .8)
  .header-fixed
    position fixed
    top 0
    left 0
    right 0
    line-height: $headerHeight
    padding 0 .7rem
    background $bgColor
    text-align center
    color #fff
    font-size .32rem
    ellipsis()
    .header-fixed-back
      position absolute
      top 0
      left 0
      width .7rem
      font-size: .6rem
      padding-left:.05rem
</style>
