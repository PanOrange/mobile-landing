<template>
  <div class="slider-holder">
    <swiper :options="swiperOption">
      <swiper-slide><img class="slide-img" src="../assets/client1.png" alt="screen"></swiper-slide>
      <swiper-slide><img class="slide-img" src="../assets/client2.png" alt="screen"></swiper-slide>
      <swiper-slide><img class="slide-img" src="../assets/client3.png" alt="screen"></swiper-slide>
      <swiper-slide><img class="slide-img" src="../assets/client4.png" alt="screen"></swiper-slide>
      <swiper-slide><img class="slide-img" src="../assets/client5.png" alt="screen"></swiper-slide>
      <swiper-slide><img class="slide-img" src="../assets/client6.png" alt="screen"></swiper-slide>
    </swiper>
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
        slidesPerView: 'auto',
        breakpoints: {
          700: {
            loopedSlides: 6,
            slidesPerView: 'auto'
          },
          320: {
            loopedSlides: 2,
            slidesPerView: 'auto'
          }
        },
        spaceBetween: 30,
        grabCursor: true,
        loop: true,
        loopedSlides: 6,
        height: 50
        // autoplay: {
        //   delay: 2500,
        //   disableOnInteraction: false
        // }
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass" scoped>
  @import '../sass/variables'
  @import '../sass/mixins'

  .slider-holder
    width: 100%
    padding: 24px 0
    overflow: hidden
    .swiper-slide
      width: auto
    /*.slide-img*/
      /*height: 50px*/
    /*.slides*/
      /*position: absolute*/
      /*top: 0*/
      /*left: 0*/
      /*height: 100%*/
      /*.slide*/
        /*height: 100%*/
        /*img*/
          /*width: 100%*/
</style>
