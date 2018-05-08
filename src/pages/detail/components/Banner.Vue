<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1702/df/df60e318301fd2a2a3.water.jpg_600x330_491e47d2.jpg" alt="">
      <div class="banner-info">
        <div class="banner-title">
          韶山旅客换乘中兴
        </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe650;</span>
          39
        </div>
      </div>
    </div>
    <common-gallary
      :imgs="imgs"
      v-show="showGallary"
      @close="handleGallaryClick"
    >
    </common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1411/1a/5582f9f24bc50b475a8cbda4c5ac8d24.water.jpg_r_800x800_e9fe596b.jpg',
          'http://img1.qunarzz.com/sight/p0/1505/10/100d2e82848fb2.water.jpg_r_800x800_5b03aa73.jpg']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClick () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      padding-left: 10px
      line-height: 30px
      color: #fff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-tittle
        flex: 1
        font-size: 16px
        padding: 0 10px
      .banner-number
        height: 16px
        line-height: 16px
        margin-top: 7px
        padding: 0 20px
        border-radius: 10px
        background: rgba(0, 0, 0, .8)
        font-size: 12px
        .banner-icon
          font-size: 12px
</style>
