<template>
  <header class="header">
    <div class="container">
      <div class="block">
        <a href="#" class="logo">
          <img src="../assets/logo.png" alt="">
        </a>
        <Menu></Menu>
      </div>
    </div>
  </header>
</template>

<script>
import Menu from './Menu'

export default {
  name: 'Header',
  components: {
    Menu
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
      width: 140px
      cursor: pointer
      img
        width: 100%
</style>
