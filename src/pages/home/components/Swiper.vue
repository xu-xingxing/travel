<template>
    <div>
        <div class="wraper">
            <swiper :options="swiperOption" ref="mySwiper" v-if="showSwiper">
                <swiper-slide v-for="item of swiperList" :key="item.id">
                    <img class="swiper-image" :src="item.imgUrl" alt="">
                </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>
            </swiper>
        </div>
    </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: ['swiperList'],
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    showSwiper () {
      return this.swiperList.length
    }
  }
}
</script>

<style lang="stylus" scoped>
.wraper >>> .swiper-pagination-bullet-active
        background: #fff;
.wraper
    overflow:hidden;
    width: 100%
    height: 0
    padding-bottom: 31.25%
    background-color: #ccc;
    .swiper-image
        width: 100%
</style>
