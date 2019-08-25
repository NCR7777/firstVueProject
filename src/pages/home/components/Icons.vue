<template>
  <div class="icons">
    <div class="icon" v-for="item of iconList" :key="item.id">
      <span :class="[item.type,'icon-img']"></span>
      <p class="icon-desc">{{item.desc}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        id: '0001',
        type: 'T1st',
        desc: '签证·WiFi'
      }, {
        id: '0002',
        type: 'T2nd',
        desc: '出境游'
      }, {
        id: '0003',
        type: 'T3rd',
        desc: '一日游'
      }, {
        id: '0004',
        type: 'T4th',
        desc: '美食林'
      }, {
        id: '0005',
        type: 'T5th',
        desc: '汽车票'
      }, {
        id: '0006',
        type: 'T6th',
        desc: '邮轮游'
      }, {
        id: '0007',
        type: 'T7th',
        desc: '超级巴士'
      }, {
        id: '0008',
        type: 'T8th',
        desc: '攻略'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles'
  @import '~styles/mixins'
  .icons
    overflow: hidden
    margin-left: 5%
    margin-right: 5%
    .icon
      overflow: hidden
      float: left
      width:25%
      padding-top: 2%
      margin-bottom: 2%
      text-align: center
      .icon-img
        display:inline-block
        width: 33px
        height: 33px
        margin: 0 auto;
        background: url(/static/index-icons-backgroud.png) no-repeat
        background-size: 374px 130px
      .T1st
        background-position: -35px -12px
      .T2nd
        background-position: -124px -12px
      .T3rd
        background-position: -212px -12px
      .T4th
        background-position: -298px -79px
      .T5th
        background-position: -35px -79px
      .T6th
        background: url(/static/index-icons-backgroud-alone.png) no-repeat
        background-size: 27px 27px
        background-position: 3px 6px
      .T7th
        background-position: -212px -79px
      .T8th
        background-position: -298px -12px
      .icon-desc
        margin-top: .1rem
        line-height: .44rem
        height: .44rem
        box-sizing: border-box
        color: $darkTextColor
        ellipsis()
</style>
