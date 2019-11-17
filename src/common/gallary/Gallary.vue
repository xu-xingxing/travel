<template>
  <div class="container" @click="hanleGallayClick">
    <div class="wrap">
      <swiper :options="swiperOptions">
        <swiper-slide v-for="(pic, index) in imgs" :key="index">
          <img class="gallary-image" :src="pic" />
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
  </div>
  </div>
</template>
<script>
export default {
  name: 'CommonGallary',
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  methods: {
    hanleGallayClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
.container >>> .swiper-container {
  overflow: inherit;
}
.container {
  z-index: 3
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background: #000;
  .wrap {
    width: 100%;
    height: 0;
    padding-bottom: 100%;
    .gallary-image {
      width: 100%;
    }
    .swiper-pagination {
      color: #fff;
      bottom: -1rem;
    }
  }
}
</style>
