<template>
  <div class="home-learn">
    <div class="container-fixed">
      <div class="block">
        <transition
          appear
          v-on:enter="onEnter"
        >
          <div class="column-center">
            <h1>Perfect landing page for any App</h1>
            <p>You can create custom iOS and macOS apps for your business using Swift, our open source programming language. Apps that have the power to transform workflows, improve client relationships, and boost your productivity.</p>
           <div class="btn-holder">
             <a href="#" class="btn">Learn more<i class="fa fa-chevron-circle-right"></i></a>
           </div>
          </div>
        </transition>
        <div class="img-block">
          <div class="img-part1">
            <img class="bg" src="../../assets/detailed-screen.png" alt="">
            <img class="screen" src="../../assets/screen5.jpg" alt="">
          </div>
          <div class="img-part2">
            <img class="bg" src="../../assets/iphone-black.png" alt="">
            <img class="screen" src="../../assets/screen6.jpg" alt="">
          </div>
          <div class="img-part3">
            <img class="bg" src="../../assets/iPhone-gold.png" alt="">
            <img class="screen" src="../../assets/screen7.jpg" alt="">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { TimelineMax, Power4 } from 'gsap'
import 'waypoints/lib/noframework.waypoints.min'

export default {
  methods: {
    onEnter (el, done) {
      const tl = new TimelineMax({ onComplete: done })
      const wp1 = new Waypoint({
        element: el,
        handler: () => {
          tl.play()
        },
        offset: '80%'
      })

      console.log(wp1)

      tl.set(el.children, { autoAlpha: 0, top: '40px' })
      tl.pause()
      tl.to(el.children[0], 1, { autoAlpha: 1, top: 0, ease: Power4.easeOut })
      tl.to(el.children[1], 1.8, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=0.8')
      tl.to(el.children[2], 1.8, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=1.2')
    }
  }
}
</script>

<style lang="sass" scoped>
  @import '../../sass/variables'
  @import '../../sass/mixins'

  .container
    @extend %container

  .container-fixed
    @extend %container-fixed

  .home-learn
    background-color: #383e40

  .block
    position: relative
    display: block
    padding: 100px 0 0
    text-align: center
    h1
      @extend %heading-main
      margin: 0 0 26px
      position: relative
    p
      @extend %text-main
      position: relative
      .home-landing &
        +bp(med)
          width: 320px
  .column-center
    +bp(tab)
      max-width: 70%
      margin: 0 auto
      padding: 0 30px
    .btn-holder
      position: relative
    .btn
      @extend %btn
      width: 100%
      margin: 10px 0 80px
      padding: 10px 16px
      font-family: $Roboto
      font-size: 18px
      font-weight: 400
      line-height: 1.2
      border-radius: 30px
      border: 2px solid $lightblue
      color: $lightblue
      +bp(400)
        width: auto
      +bp(med)
        font-size: 20px
        padding: 12px 40px
      &:hover
        color: $white
        background-color: $lightblue
      i
        margin-left: 8px

  .img-block
    position: relative
    overflow: hidden
    height: 160px
    margin: 0 auto
    max-width: 250px
    +bp(mob)
      max-width: 400px
      height: 240px
    +bp(560)
      max-width: 920px
      margin: 0 auto
    +bp(med)
      height: 460px
    +bp(lg)
      height: 530px
      max-width: 100%
    >div
      position: absolute
      top: 0
      height: 100%
      width: 30%

    .bg
      position: absolute
      top: 0
      left: 0
      width: 100%
    .screen
      position: absolute
      top: 11%
      left: 6%
      width: 88%
      +bp(560)
        top: 15%
      +bp(tab)
        top: 20.5%
      +bp(med)
        top: 14.5%
    .img-part1
      width: 30%
      top: 15%
      left: 15%
      z-index: 7
    .img-part2
      left: 50%
      transform: translate(-50%)
      z-index: 8
    .img-part3
      width: 30%
      top: 15%
      right: 15%
      z-index: 7

</style>
