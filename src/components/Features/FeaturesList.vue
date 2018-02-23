<template>
  <div class="features-list">
    <div class="container-fixed">
      <div class="block">
        <div class="column-center">
          <h1>Main Features</h1>
          <p>Shocase main features of your app or tell them how the app works using a three step process. Its easy. You may also add some descriptions to this section.</p>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="gallery">
        <ul>
          <li v-for="item in gallery" :key="item.icon">
            <i class="pe" :class="item.icon" aria-hidden="true"></i>
            <h3>{{item.title}}</h3>
            <p>{{item.text}}</p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
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
    p
      @extend %text-main
      margin-bottom: 60px
      +bp(med)
        padding: 0 40px
    .column-center
      +bp(tab)
        max-width: 70%
        margin: 0 auto
        padding: 0 30px
  .gallery
    ul
      display: flex
      flex-wrap: wrap
      margin: 0
      padding: 0 0 40px
      +bp(620)
        padding: 0 0 100px
      li
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
