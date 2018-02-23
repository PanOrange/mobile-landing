<template>
  <header class="header">
    <div class="container">
      <div class="block">
        <transition
          v-on:enter="enter"
          v-bind:css="false"
          appear
        >
          <a href="#" class="logo">
            <img src="../assets/logo.png" alt="">
          </a>
        </transition>
        <Menu></Menu>
      </div>
    </div>
  </header>
</template>

<script>
import Menu from './Menu'
import {
  TimelineMax,
  // TweenMax,
  Power4
} from 'gsap'

export default {
  name: 'Header',
  components: {
    Menu
  },
  methods: {
    enter (el, done) {
      const tl = new TimelineMax({
        onComplete: done
      })

      tl.set(el, { autoAlpha: 0, top: '-70px', scale: 0.9 })
      tl.to(el, 1, { autoAlpha: 1, top: '-5px', scale: 1, ease: Power4.easeIn })
      tl.to(el, 0.5, { top: 0 })
    }
    // , leave (el, done) {
    //   TweenMax.fromTo(el, 1, {
    //     autoAlpha: 1,
    //     scale: 1
    //   }, {
    //     autoAlpha: 0,
    //     scale: 0.8,
    //     ease: Power4.easeOut,
    //     onComplete: done
    //   })
    // }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass" scoped>
  @import '../sass/variables'
  @import '../sass/mixins'

  .header
    border-bottom: 1px solid $light

  .container
    @extend %container

  .block
    display: flex
    align-items: center
    justify-content: space-between
    height: 74px
    .logo
      position: relative
      width: 140px
      cursor: pointer
      img
        width: 100%
</style>
