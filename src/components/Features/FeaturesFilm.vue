<template>
  <div class="features-film">
    <div class="container">
      <div class="block">
        <div class="content">
          <i class="pe pe-7s-film" aria-hidden="true"></i>

          <h2>Watch the film</h2>
          <h4>A video is worth thousand words</h4>
          <p>Apps that have the power to transform workflows, improve client relationships, and boost your productivity.</p>
        </div>
        <div class="film">
          <img src="../../assets/video-img.jpg" alt="video">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="sass" scoped>
  @import '../../sass/variables'
  @import '../../sass/mixins'

  .features-film
    background-color: $light
  .container
    @extend %container
  .block
    display: flex
    flex-direction: column
    align-items: center
    justify-content: space-between
    padding: 40px 0
    +bp(400)
      padding: 40px 10px
    +bp(tab)
      align-items: stretch
      flex-direction: row
      padding: 100px 10px
    .content
      +bp(tab)
        padding-right: 80px
      i
        font-size: 60px
        color: $lightblue
      h2
        margin: 30px 0 17px
        font-family: $Roboto
        font-weight: 100
        font-size: 32px
        color: $white

      h4
        margin: 0 0 26px
        font-family: $Roboto
        font-weight: 100
        font-size: 24px
        color: $white
      p
        font-family: $Roboto
        font-weight: 300
        font-size: 16px
        line-height: 1.5
        color: $white
    .film
      width: 100%
      border-radius: 30px
      overflow: hidden
      img
        width: 100%
        +bp(tab)
          height: 100%
</style>
