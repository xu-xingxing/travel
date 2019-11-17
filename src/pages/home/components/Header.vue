<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont back-icon">&#xe6ed;</div>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe70a;</span>
            输入城市游玩主题
        </div>
        <router-link to="/city">
            <div class="header-right">
               {{this.city}}
            <span class="iconfont arrow-icon">&#xe6b5;</span>
        </div>
        </router-link>
    </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .header
        display: flex;
        height: $headerHeight;
        line-height: $headerHeight;
        background: $bgColor;
        color: #fff;
        .header-left
            width: .64rem;
            float: left;
            .back-icon
                text-align:center;
                font-size: .6rem;
        .header-input
            flex:1;
            height: .62rem;
            line-height: .62rem;
            margin-top: .12rem;
            margin-left: .2rem;
            padding-left: .2rem;
            background: #fff;
            border-radius: .1rem;
            color: #ccc;
        .header-right
            min-width: 1.04rem;
            padding: 0 .1rem;
            float: right;
            text-align: center;
            color: #fff;
            .arrow-icon
                margin-left: -.1rem;
                font-size: .24rem;
</style>
