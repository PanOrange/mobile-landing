<template>
  <div id="app">
    <Header />
      <main>
        <Home />
        <Features />
        <Pricing />
      </main>
    <Footer />
  </div>
</template>

<script>
import Header from './containers/Header'
import Home from './containers/Home'
import Features from './containers/Features'
import Pricing from './containers/Pricing'
import Footer from './containers/Footer'

export default {
  name: 'App',
  components: {
    Header, Home, Features, Pricing, Footer
  }
}
</script>

<style lang="sass">
@import "sass/normalize.min.css"
@import "sass/variables"

// Fonts
@import url("https://fonts.googleapis.com/css?family=Roboto:100,300,400,500,700,900")
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css")
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/fonts/fontawesome-webfont.svg")

*
  box-sizing: border-box

#app
  min-height: 100vh
  background-color: $dark
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  color: #2c3e50
</style>
