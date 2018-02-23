<template>
  <div class="home-intro">
    <div class="container-fixed">
      <div class="block">
        <div class="column">
          <SliderPhone></SliderPhone>
        </div>
        <transition
          v-on:enter="onEnter"
          appear
        >
          <div class="column column-vertical">
            <h1>Create an App Landing Page. No Coding required</h1>
            <p>You can create custom iOS and macOS apps for your business using Swift, our open source programming language. Apps that have the power to transform workflows, improve client relationships, and boost your productivity.</p>
            <div class="button-block">
              <a href="" class="btn btn-apple"><i class="fa fa-apple"></i>App Store</a>
              <a href="" class="btn btn-android"><i class="fa fa-android"></i>Play Store</a>
            </div>
            <p class="notes">Version required ios 10 or later, Android Kitkat or later</p>
          </div>
        </transition>
      </div>
    </div>
    <div class="home-partners">
      <div class="container">
        <div class="block">
          <SliderPartners></SliderPartners>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { TimelineMax, Power4 } from 'gsap'

import SliderPhone from '../SliderPhone'
import SliderPartners from '../SliderPartners'
export default {
  components: {
    SliderPhone, SliderPartners
  },
  methods: {
    onEnter (el, done) {
      console.log(el.children)
      const tl = new TimelineMax({
        onComplete: done
      })

      tl.set(el.children, { autoAlpha: 0, top: '40px' })
      tl.to(el.children[0], 1, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '0.5')
      tl.to(el.children[1], 1.2, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=0.8')
      tl.to(el.children[2], 1.2, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=0.8')
      tl.to(el.children[3], 1.2, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=0.8')
    }
  }
}
</script>

<style lang="sass" scoped>
  @import '../../sass/variables'
  @import '../../sass/mixins'

  .container-fixed
    @extend %container-fixed

  .container
    @extend %container

  .block
    display: flex
    align-items: flex-start
    justify-content: space-between
    flex-direction: column-reverse
    +bp(tab)
      flex-direction: row
    .column
      width: 100%
      overflow: hidden
      &:first-child
        align-self: flex-end
      +bp(tab)
        width: 50%
        padding: 0 10px
      &.column-vertical
        flex-direction: column
        padding-top: 40px
        +bp(med)
          padding-top: 9em
    h1
      @extend %heading-main
      position: relative
      margin: 0 0 26px
    p
      @extend %text-main
      position: relative
      &.notes
        margin: 0
        color: #a1a4ab
    .button-block
      position: relative
      .btn
        @extend %btn
        width: 100%
        margin-bottom: 16px
        padding: 10px 16px
        font-family: $Roboto
        font-size: 18px
        font-weight: 400
        line-height: 1.2
        border-radius: 30px
        +bp(400)
          width: auto
        +bp(med)
          font-size: 20px
          padding: 12px 40px
        &.btn-apple
          margin-right: 16px
          border: 2px solid $lightblue
          color: $lightblue
          &:hover
            color: $white
            background-color: $lightblue
        &.btn-android
          border: 2px solid $lightgreen
          color: $lightgreen
          &:hover
            color: $white
            background-color: $lightgreen
        &:first-child
          margin-right: 16px
        i
          margin-right: 8px
  .home-partners
    background-color: #383e40
</style>
