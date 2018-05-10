<template>
  <div>
    <router-link
      tag="div"
      to="/"
      class="header-abs"
      v-show="showAbs"
      :style="opacityFixedStyle"
    >
      <div class="iconfont head-back header-abs-back">&#xe624;</div>
    </router-link>
    <div
      class="header-fixed"
      v-show="!showAbs"
      :style="opacityStyle"
    >
      景点详情
      <router-link to="/">
        <div class="iconfont head-fixed-back">&#xe624;</div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Detail-Header',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      },
      opacityFixedStyle: {
        opacity: 1
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = (top - 60) / 80
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        let opacity = (60 - top) / 60
        opacity = opacity < 0.5 ? 0.5 : opacity
        this.opacityFixedStyle = { opacity }
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-abs
    position: fixed
    left: 10px
    top: 10px
    width: 40px
    height: 40px
    line-height: 40px
    border-radius: 20px
    text-align: center
    background: rgba(0, 0, 0, .8)
    .header-abs-back
      color: #fff
      font-size: 20px
  .header-fixed
    position: fixed
    top: 0
    left: 0
    right: 0
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #fff
    background: $bgColor
    font-size: 16px
    .head-fixed-back
      position: absolute
      top: 0
      left: 0
      width: 32px
      text-align: center
      font-size: 20px
      color: #fff
</style>
