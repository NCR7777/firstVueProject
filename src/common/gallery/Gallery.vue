<template>
    <div class="container" @click="handleGalleryClick">
      <div class="wrapper">
        <swiper :options="swiperOption">
          <swiper-slide v-for="(item, index) of GalleryImgList" :key="index">
            <img class="gallery-img" :src="item.imgUrl" :alt="index">
          </swiper-slide>
          <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
      </div>
    </div>
</template>

<script>
export default {
  name: 'CommonGallery',
  props: {
    GalleryImgList: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        mousewheelControl: true,
        observeParents: true,
        observer: true,
        loop: true
      }
    }
  },
  methods: {
    handleGalleryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow inherit
  .container
    display flex
    flex-direction column
    justify-content center
    z-index 1
    position fixed
    left 0
    right 0
    top 0
    bottom 0
    background #000
    .wrapper
      width 100%
      height 0
      padding-bottom 55%
      .gallery-img
        width 100%
      .swiper-pagination
        color #fff
        bottom -3.2rem
        font-size .24rem
</style>
