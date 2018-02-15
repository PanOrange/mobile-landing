<template>
  <section class="home-view">
    <div class="home-intro">
      <div class="container-fixed">
        <div class="block">
          <div class="column">
            <SliderPhone></SliderPhone>
          </div>
          <div class="column column-vertical">
            <h1>Create an App Landing Page. No Coding required</h1>
            <p>You can create custom iOS and macOS apps for your business using Swift, our open source programming language. Apps that have the power to transform workflows, improve client relationships, and boost your productivity.</p>
            <div class="button-block">
              <a href="" class="btn btn-apple"><i class="fa fa-apple"></i>App Store</a>
              <a href="" class="btn btn-android"><i class="fa fa-android"></i>Play Store</a>
            </div>
            <p class="notes">Version required ios 10 or later, Android Kitkat or later</p>
          </div>
        </div>
      </div>
    </div>
    <div class="home-partners">
      <div class="container">
        <div class="block">
          <SliderPartners></SliderPartners>
        </div>
      </div>
    </div>
    <div class="home-landing">
      <div class="container-fixed">
        <div class="block">
          <div class="text-block">
            <h1>Beautiful Landing Page Template</h1>
            <p>You can create custom iOS and macOS apps for your business using Swift, our open source programming language. Apps that have the power to transform workflows, improve client relationships, and boost your productivity.</p>
          </div>
          <div class="img-fluid">
            <img src="../assets/isometric-view.png" alt="pic">
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import SliderPhone from '../components/SliderPhone'
import SliderPartners from '../components/SliderPartners'
export default {
  components: {
    SliderPhone, SliderPartners
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass" scoped>
  @import '../sass/variables'
  @import '../sass/mixins'

  .container
    @extend %container

  .container-fixed
    @extend %container-fixed

  .block
    display: flex
    align-items: flex-start
    justify-content: space-between
    flex-direction: column
    .home-intro &
      flex-direction: column-reverse
      +bp(tab)
        flex-direction: row
    .home-landing &
      padding: 70px 0
      +bp(tab)
        padding: 100px 0

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
      margin: 0 0 26px
    p
      @extend %text-main
      .home-landing &
        +bp(med)
          width: 320px
      &.notes
        margin: 0
        color: #a1a4ab
    .button-block
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

  .home-partners
    background-color: #383e40

</style>
