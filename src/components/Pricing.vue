<template>
  <div></div>
</template>

<script>
export default {
  // components: {
  //   Menu
  // }
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
