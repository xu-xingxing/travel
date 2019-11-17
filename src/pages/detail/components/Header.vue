<template>
  <div>
    <router-link tag="div" to="/" class="header-abs">
      <div class="iconfont header-abs-back">&#xe6ed;</div>
    </router-link>
    <div class="header-fixed" v-show="!showabs" :style="opacityStyle">
      <router-link to="/">
        <div class="iconfont header-fixed-back">&#xe6ed;</div>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showabs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll(){
      console.log('scroll')
      const top = document.documentElement.scrollTop
      if(top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showabs = false
      } else {
          this.showabs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-abs
    position: absolute
    left: .2rem
    top: .2rem
    width: .8rem
    line-height: .8rem
    height: .8rem
    text-align: center
    border-radius: .4rem
    background: rgba(0, 0, 0, .8)
    .header-abs-back
      color: #fff
      font-size: .6rem
  .header-fixed
    position: fixed
    top: 0;
    left: 0;
    right: 0;
    height: $headerHeight;
    line-height: $headerHeight;
    text-align: center;
    color: #fff;
    background: $bgColor;
    font-size: .32rem
    .header-fixed-back
        position: absolute;
        left: 0;
        top: 0;
        width: .64rem;
        font-size: .6rem;
        color: #fff;
</style>