<template>
  <div class="slider">
    <img src="../assets/adult-hand-dark.png" alt="">
    <div class="slider-holder">
      <swiper :options="swiperOption">
        <swiper-slide><img class="slide-img" src="../assets/screen1.jpg" alt="screen"></swiper-slide>
        <swiper-slide><img class="slide-img" src="../assets/screen2.jpg" alt=""></swiper-slide>
        <swiper-slide><img class="slide-img" src="../assets/screen3.jpg" alt="screen"></swiper-slide>
        <swiper-slide><img class="slide-img" src="../assets/screen4.jpg" alt="screen"></swiper-slide>
      </swiper>
    </div>
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'

import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
  components: {
    swiper, swiperSlide
  },
  data () {
    return {
      swiperOption: {
        grabCursor: true,
        loop: true,
        autoplay: {
          delay: 2500,
          disableOnInteraction: false
        }
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass" scoped>
  @import '../sass/variables'
  @import '../sass/mixins'

  .slider
    position: relative
    max-width: 484px
    margin-bottom: -5px
    overflow: hidden
    z-index: 10
    >img
      width: 100%
    .slider-holder
      position: absolute
      width: 40.2%
      height: 48.2%
      top: 16%
      left: 39.1%
      overflow: hidden
      .slide-img
        width: 100%
    .slides
      position: absolute
      top: 0
      left: 0
      height: 100%
      .slide
        height: 100%
        img
          width: 100%
</style>
