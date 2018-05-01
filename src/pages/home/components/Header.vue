<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont back-icon">&#xe624;</div>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题
        </div>
        <div class="header-right">城市
            <span class="iconfont arrow-icon">&#xe6aa;</span>
        </div>
    </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .header
        display: flex
        line-height: 43px
        background: $bgColor
        color: #fff
        .header-left
            width: 32px
            float: left
            .back-icon
                text-align: center
                font-size: 20px
        .header-input
            flex: 1
            margin-top: 6px
            height: 32px
            line-height: 32px
            margin-left: 10px
            padding-left: 10px
            background: #fff
            border-radius: 5px
            color: #ccc
        .header-right
            width: 63px
            float: right
            text-align: center
            .arrow-icon
                margin-left: -2px
                font-size: 12px
</style>
