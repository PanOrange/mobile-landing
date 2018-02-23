<template>
  <div class="home-landing">
    <div class="container-fixed">
      <div class="block">
        <transition
          appear
          v-on:enter="onEnter"
        >
          <div class="text-block">
            <h1>Beautiful Landing Page Template</h1>
            <p>You can create custom iOS and macOS apps for your business using Swift, our open source programming language. Apps that have the power to transform workflows, improve client relationships, and boost your productivity.</p>
          </div>
        </transition>
        <div class="img-fluid">
          <img src="../../assets/isometric-view.png" alt="pic">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { TimelineMax, Power4 } from 'gsap'

import { getOffset } from '../../helpers'

export default {
  methods: {
    onEnter (el, done) {
      const tl = new TimelineMax({ onComplete: done })
      window.addEventListener('scroll', () => {
        const bottomOffset = (window.scrollY + window.innerHeight - getOffset(el).top)
        if (bottomOffset > 100) {
          tl.play()
        }
      })
      tl.set(el.children, { autoAlpha: 0, top: '40px' })
      tl.pause()
      tl.to(el.children[0], 1.8, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '0.5')
      tl.to(el.children[1], 1.8, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=1.5')
    }
  }
}
</script>

<style lang="sass" scoped>
  @import '../../sass/variables'
  @import '../../sass/mixins'

  .container-fixed
    @extend %container-fixed

  .block
    display: flex
    align-items: flex-start
    justify-content: space-between
    flex-direction: column
    padding: 70px 0
    +bp(tab)
      padding: 100px 0
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
    .img-fluid
      position: relative
      width: 100%
      +bp(med)
        margin-top: -16%
      +bp(lg)
        margin-top: -22%
      img
        width: calc(100% + 30px)
        margin: 0 -15px

</style>
