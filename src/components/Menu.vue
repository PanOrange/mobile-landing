<template>
  <nav>
    <ul>
      <li v-for="(item, index) in menu" :key="index">
        <a :href="item.link" :class="{active: activeItem === item.title}">{{ item.title }}</a>
      </li>
    </ul>
  </nav>
</template>

<script>
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
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass" scoped>
  @import '../sass/variables'
  @import '../sass/mixins'

  .container
    @extend %container

  ul
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
