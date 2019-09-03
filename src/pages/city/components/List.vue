<template>
    <div class="list" ref="wrapper">
      <div>
        <div class="area">
          <div class="title border-topbottom">当前城市</div>
          <div class="button-list">
            <router-link to="/">
              <div class="button-wrapper">
                <div class="button active">{{this.currentCity}}</div>
              </div>
            </router-link>
          </div>
        </div>
        <div class="area">
          <div class="title border-topbottom">热门城市</div>
          <div class="button-list">
            <ul>
              <li class="button-wrapper" v-for="item of hotCities" :key="item.id" @click="handleCityClick(item.name)">
                <div class="button">{{item.name}}</div>
              </li>
            </ul>
          </div>
        </div>
        <div class="area" v-for="(item, key) of cities" :key="key" :ref="key">
          <div class="title border-topbottom">{{key}}</div>
          <div class="item-list">
            <ul>
              <li class="item border-bottom" v-for="innerItem of item" :key="innerItem.id" @click="handleCityClick(innerItem.name)">
                <div>{{innerItem.name}}</div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'CityList',
  props: {
    hotCities: Array,
    cities: Object,
    letter: String
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper, {
      click: true
    })
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .border-topbottom
    &:before
      border-color #aaa
    &:after
      border-color #aaa
  .border-bottom
    &:before
      border-color #aaa
  .list
    overflow hidden
    position absolute
    top 2.28rem
    left 0
    right 0
    bottom 0
    .title
      line-height .44rem
      background $bgGrayColor
      padding-left .2rem
      color #666
      font-size .26rem
    .button-list
      overflow hidden
      padding .1rem .6rem .1rem .1rem
      .button-wrapper
        float left
        width 33.33%
        .button
          margin .1rem
          padding .1rem 0
          text-align center
          border .02rem solid #ccc
          border-radius .06rem
        .active
          background $bgColor
          color #fff
          border .02rem solid $bgColor
    .item-list
      .item
        line-height .76rem
        padding-left .2rem
</style>
