<template>
  <div>
      <div class="recommend-title">周末去哪儿</div>
      <ul>
          <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
              <div class="item-img-warpper">
                  <img :src="item.imgUrl" :alt="item.title" class="item-img">
              </div>
              <div class="item-info">
                  <p class="item-title">{{item.title}}</p>
                  <p class="item-desc">{{item.desc}}</p>
              </div>
          </li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/ae/11f076c6cb7c47.jpg_r_640x214_6f643489.jpg',
        title: '古北水镇',
        desc: '古北水镇是一个神奇的水镇，那里生活着一群可爱的人们'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/fb/302620ed8350f8.jpg_r_640x214_25a07cb4.jpg',
        title: '北京野生动物园',
        desc: '北京野生动物园是一个非常好玩的野生动物园，里面有各种的野生动物'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1603/56/33894ef918e1a8.jpg_r_640x214_a9de6b4e.jpg',
        title: '世界花卉大观园',
        desc: '世界花卉大观园是一个超级漂亮的花卉观园'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/39/d61194f054f1f4.jpg_r_640x214_03da9c61.jpg',
        title: '北京欢乐谷',
        desc: '北京欢乐谷是一个特别好玩的欢乐谷'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/mixins.styl'
    .recommend-title
        margin-top: 10px
        line-height: 40px
        background: #eee
        text-indent: 10px
    .item-img-warpper
        overflow: hidden
        height: 0
        padding-bottom: 33.9%
    .item-img
        width: 100%
    .item-info
        padding: 5px
    .item-title
        line-height: 27px
        font-size: 16px
        ellipsis()
    .item-desc
        line-height: 20px
        color: #ccc
        ellipsis()

</style>
