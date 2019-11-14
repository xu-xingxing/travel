<template>
    <div class="header">
        城市选择
        <router-link to="/">
            <div class="iconfont head-back">&#xe6ed;</div>
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
        overflow: hidden;
        height: $headerHeight;
        line-height: $headerHeight;
        text-align: center;
        color: #fff;
        background: $bgColor;
        position: relative;
        .head-back
           position: absolute;
           left: 0;
           top: 0;
           width: .64rem;
           text-align: center;
           font-size: .6rem;
           color: #fff;
</style>
