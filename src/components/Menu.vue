<template>
  <nav>
    <transition
      v-on:enter="enter"
      v-bind:css="false"
      appear
    >
      <ul>
        <li v-for="(item, index) in menu" :key="index">
          <a :href="item.link" :class="{active: activeItem === item.title}">{{ item.title }}</a>
        </li>
      </ul>
    </transition>
  </nav>
</template>

<script>
import { TimelineMax, Power4 } from 'gsap'

export default {
  name: 'Menu',
  data () {
    return {
      activeItem: 'Home',
      menu: [
        {title: 'Home', link: '#'},
        {title: 'Features', link: '#'},
        {title: 'Pricing', link: '#'},
        {title: 'Blog', link: '#'},
        {title: 'Contact', link: '#'}
      ]
    }
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
  }
}
</script>

<style lang="sass" scoped>
  @import '../sass/variables'
  @import '../sass/mixins'

  .container
    @extend %container

  ul
    position: relative
    display: none
    align-items: center
    margin: 0
    padding: 0
    +bp(tab)
      display: flex
    li
      margin-left: 30px
      list-style: none
    a
      @extend %btn
      padding: 4px 0
      text-transform: uppercase
      color: $white
      border-bottom: 2px solid transparent
      &:hover
        color: $lightblue
      &.active
        color: $lightblue
        border-bottom: 2px solid $lightblue
</style>
