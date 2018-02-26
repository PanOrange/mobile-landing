<template>
  <div class="features-list">
    <div class="container-fixed">
      <div class="block">
        <transition
          appear
          v-on:enter="onEnter"
        >
          <div class="column-center">
            <h1>Main Features</h1>
            <p>Shocase main features of your app or tell them how the app works using a three step process. Its easy. You may also add some descriptions to this section.</p>
          </div>
        </transition>
      </div>
    </div>
    <div class="container">
      <transition
        appear
        v-on:enter="onEnterGallery"
      >
        <ul class="gallery">
          <li v-for="item in gallery" :key="item.icon">
            <i class="pe" :class="item.icon" aria-hidden="true"></i>
            <h3>{{item.title}}</h3>
            <p>{{item.text}}</p>
          </li>
        </ul>
      </transition>
    </div>
  </div>
</template>

<script>
import { TimelineMax, Power4 } from 'gsap'
import 'waypoints/lib/noframework.waypoints.min'
export default {
  data: function () {
    return {
      gallery: [
        {
          icon: 'pe-7s-graph1',
          title: 'Simple & Powerful',
          text: 'Apps that have the power to transform workflows, improve client relationships, and boost your productivity.'
        },
        {
          icon: 'pe-7s-gleam',
          title: 'Minimal design',
          text: 'Apps that have the power to transform workflows, improve client relationships, and boost your productivity.'
        },
        {
          icon: 'pe-7s-config',
          title: 'Powerful Integrations',
          text: 'Apps that have the power to transform workflows, improve client relationships, and boost your productivity.'
        },
        {
          icon: 'pe-7s-edit',
          title: 'Customizable',
          text: 'Apps that have the power to transform workflows, improve client relationships, and boost your productivity.'
        },
        {
          icon: 'pe-7s-graph3',
          title: 'Improve your sales',
          text: 'Apps that have the power to transform workflows, improve client relationships, and boost your productivity.'
        },
        {
          icon: 'pe-7s-help2',
          title: '24/7 Support',
          text: 'Apps that have the power to transform workflows, improve client relationships, and boost your productivity.'
        }
      ]
    }
  },
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

      tl.set(wp1.element.children, { autoAlpha: 0, top: '20px' })
      tl.pause()
      tl.to(el.children[0], 1, { autoAlpha: 1, top: 0, ease: Power4.easeOut })
      tl.to(el.children[1], 1.8, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=0.8')
    },
    onEnterGallery (el, done) {
      const tl = new TimelineMax({ onComplete: done })
      const wp2 = new Waypoint({
        element: el,
        handler: () => {
          tl.play()
        },
        offset: '80%'
      })

      tl.set(wp2.element.children, { autoAlpha: 0, top: '10px' })
      tl.pause()
      tl.to(el.children[0], 0.6, { autoAlpha: 1, top: 0, ease: Power4.easeOut })
      tl.to(el.children[1], 0.6, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=0.3')
      tl.to(el.children[2], 0.6, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=0.3')
      tl.to(el.children[3], 0.6, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=0.3')
      tl.to(el.children[4], 0.6, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=0.3')
      tl.to(el.children[5], 0.6, { autoAlpha: 1, top: 0, ease: Power4.easeOut }, '-=0.3')
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
  .block
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
      margin-bottom: 60px
      +bp(med)
        padding: 0 40px
    .column-center
      +bp(tab)
        max-width: 70%
        margin: 0 auto
        padding: 0 30px
  .gallery
    display: flex
    flex-wrap: wrap
    margin: 0
    padding: 0 0 40px
    +bp(620)
      padding: 0 0 100px
    li
      position: relative
      display: flex
      flex-direction: column
      align-items: center
      list-style: none
      margin: 0 auto
      padding: 20px 10px
      width: 100%
      border-bottom: 1px solid rgba(#9fa6b1, 0.2)
      &:nth-child(6)
        border-bottom: 1px solid transparent
      +bp(400)
        max-width: 380px
      +bp(620)
        max-width: 100%
        width: 50%
        &:nth-child(2n+1)
          border-right: 1px solid rgba(#9fa6b1, 0.2)
        &:nth-child(5)
          border-bottom: 1px solid transparent
      +bp(med)
        width: 33.33%
        border-right: 1px solid rgba(#9fa6b1, 0.2)
        &:nth-child(1),
        &:nth-child(2),
        &:nth-child(3)
          padding-top: 0
          border-bottom: 1px solid rgba(#9fa6b1, 0.2)
        &:nth-child(4)
          border-bottom: 1px solid transparent
        &:nth-child(3n+3)
          border-right: 1px solid transparent
      i
        color: $cyan
        font-size: 60px
      h3
        font-family: $Roboto
        font-size: 20px
        font-weight: 700
        color: $white
      p
        @extend %text-main
        text-align: center
        color: #9fa6b1

</style>
