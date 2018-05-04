<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont head-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position: relative
    overflow: hidden
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #fff
    background: $bgColor
    font-size: 16px
    .head-back
      position: absolute
      top: 0
      left: 0
      width: 32px
      text-align: center
      font-size: 20px
      color: #fff
</style>
