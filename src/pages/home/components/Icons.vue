<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" alt="">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        mousewheelControl: true,
        observeParents: true
      },
      iconList: [{
        id: '0001',
        desc: '景点门票',
        imgUrl: '/static/index-icons/index-icon-1.png'
      }, {
        id: '0002',
        desc: '深圳必游',
        imgUrl: '/static/index-icons/index-icon-2.png'
      }, {
        id: '0003',
        desc: '暑期夜场',
        imgUrl: '/static/index-icons/index-icon-3.png'
      }, {
        id: '0004',
        desc: '海洋馆',
        imgUrl: '/static/index-icons/index-icon-4.png'
      }, {
        id: '0005',
        desc: '一日游',
        imgUrl: '/static/index-icons/index-icon-5.png'
      }, {
        id: '0006',
        desc: '深圳动物园',
        imgUrl: '/static/index-icons/index-icon-6.png'
      }, {
        id: '0007',
        desc: '世界之窗',
        imgUrl: '/static/index-icons/index-icon-7.png'
      }, {
        id: '0008',
        desc: '东部华侨城',
        imgUrl: '/static/index-icons/index-icon-8.png'
      }, {
        id: '0009',
        desc: '水上玩乐',
        imgUrl: '/static/index-icons/index-icon-9.png'
      }, {
        id: '0010',
        desc: '玩转长隆',
        imgUrl: '/static/index-icons/index-icon-10.png'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles'
  @import '~styles/mixins'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 54%
  .icons >>> .swiper-pagination
    position: absolute
    bottom: 0
  .icon
    position: relative
    overflow: hidden
    float: left
    width: 25%
    height: 0
    padding-bottom: 25%
    .icon-img
      position: absolute
      top: 0
      left: 0
      right: 0
      bottom: .44rem
      box-sizing: border-box
      padding: .1rem
      .icon-img-content
        display: block
        margin: 0 auto
        height: 100%
    .icon-desc
      position: absolute
      left: 0
      right: 0
      bottom: 0
      height: .44rem
      line-height: .44rem
      text-align: center
      color: $darkTextColor
      ellipsis()
</style>
