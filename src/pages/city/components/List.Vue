<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" v-for="item of hot" :key="item.id">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item, key) of cities" :key="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item" v-for="innerItem of item" :key="innerItem.id">{{innerItem.name}}<hr></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
      &:before
          border-color: #ccc
      &:after
          border-color: #ccc
  .list
      overflow: hidden
      position: absolute
      top: 79px
      left: 0
      right: 0
      bottom: 0
      .title
          line-height: 27px
          background: #eee
          padding-left: 10px
          color: #666
          font-size: 13px
      .button-list
          overflow: hidden
          padding: 5px 30px 5px 5px
          .button-wrapper
              float: left
              width: 33.33%
              .button
                  margin: 5px
                  padding: 5px 0
                  text-align: center
                  border: 1px solid #ccc
                  border-radius: 3px
  .item-list
      .item
          line-height: 38px
          padding-left: 10px
</style>
