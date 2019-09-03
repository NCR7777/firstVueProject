<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="this.bannerImage" alt="">
      <div class="banner-info">
        <div class="banner-title">{{this.sightName}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe678;</span>
          {{this.galleryImages.length}}
        </div>
      </div>
    </div>
    <common-gallery :GalleryImgList="this.galleryImages" v-show="showGallery" @close="handleGalleryClose"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    galleryImages: Array,
    bannerImage: String,
    galleryImagesCount: Number
  },
  data () {
    return {
      showGallery: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallery = true
    },
    handleGalleryClose () {
      this.showGallery = false
    }
  },
  components: {
    CommonGallery
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
  .banner
    position relative
    overflow hidden
    width 100%
    height 0
    padding-bottom 55%
    .banner-img
      width 100%
    .banner-info
      display flex
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      color #fff
      background-image linear-gradient(top, rgba(0,0,0,0), rgba(0, 0, 0, .5))
      .banner-title
        flex 1
        padding .2rem .2rem
        font-size .36rem
        text-shadow: 0 1px 2px rgba(0, 0, 0, .7)
        ellipsis()
      .banner-number
        position absolute
        left 0
        top -.2rem
        padding 0 .2rem
        margin-left .2rem
        line-height .35rem
        height .32rem
        border-radius .2rem
        background rgba(0, 0, 0, .8)
        vertical-align center
        .banner-icon
          font-size .24rem
</style>
