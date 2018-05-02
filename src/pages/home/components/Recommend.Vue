<template>
  <div>
      <div class="recommend-title">热销推荐</div>
      <ul>
          <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
              <img :src="item.imgUrl" :alt="item.title" class="item-img">
              <div class="item-info">
                  <p class="item-title">{{item.title}}</p>
                  <p class="item-desc">{{item.desc}}</p>
                  <button class="item-button">查看详情</button>
              </div>
          </li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1804/c8/c88bb5e69c9a9c5ea3.img.jpg_200x200_740720ff.jpg',
        title: '古北水镇',
        desc: '古北水镇是一个神奇的水镇，那里生活着一群可爱的人们'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/36/ce3d2d6c9ab44d67ae68d940b8781829.water.jpg_200x200_0938a8f2.jpg',
        title: '北京野生动物园',
        desc: '北京野生动物园是一个非常好玩的野生动物园，里面有各种的野生动物'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1803/7b/7b023b9728f0834fa3.img.jpg_200x200_5fddc1d8.jpg',
        title: '世界花卉大观园',
        desc: '世界花卉大观园是一个超级漂亮的花卉观园'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/a5/4003f9dd7bebf61eccbf64046e26d487.water.jpg_200x200_7690e4cd.jpg',
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
    .item
        overflow: hidden
        display: flex
        height: 95px
        .item-img
            width: 85px
            height: 85px
            padding: 5px
        .item-info
            flex: 1
            padding: 5px
            min-width: 0
            .item-title
                line-height: 27px
                font-size: 16px
                ellipsis()
            .item-desc
                line-height: 20px
                color: #ccc
                ellipsis()
            .item-button
                line-height: 22px
                margin-top: 8px
                background: #ff9300
                padding: 0 10px
                border-radius: 5px
                color: #fff
</style>
