<template>
    <div>
      <detail-banner :sightName="sightName" :galleryImages="galleryImages" :bannerImage="bannerImage"></detail-banner>
      <detail-header :sightName="sightName"></detail-header>
      <div class="content">
        <detail-list :categoryList="categoryList"></detail-list>
      </div>
    </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  data () {
    return {
      id: '',
      sightName: '',
      categoryList: [],
      galleryImages: [],
      bannerImage: ''
    }
  },
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.getDetailInfoSucceed)
    },
    getDetailInfoSucceed (response) {
      response = response.data
      if (response.ret && response.data) {
        const sightId = this.$route.params.id
        try {
          response.data.forEach(item => {
            if (sightId === item.id) {
              const data = item
              this.sightName = data.sightName
              this.categoryList = data.categoryList
              this.galleryImages = data.galleryImages
              this.galleryImagesCount = data.galleryImagesCount
              this.bannerImage = data.bannerImage
              throw new Error('updateData')
            }
          })
        } catch (e) {}
      }
    }
  },
  activated () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height 50rem
</style>
