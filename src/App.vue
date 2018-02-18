<template>
  <div id="app">
    <Header />
      <main>
        <HomeIntro />
        <HomeTemplate />
        <HomeLanding />
        <FeaturesList />
        <FeaturesFilm />
        <FeaturesLove />
        <FeaturesModern />
        <FeaturesStyle />
        <Reviews />
        <Gallery />
        <Stages />
        <Content />
        <Pricing />
        <Faq />
        <Team />
        <Map />
        <Contacts />
        <Store />
      </main>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header'
import HomeIntro from './components/Home/HomeIntro'
import HomeTemplate from './components/Home/HomeTemplate'
import HomeLanding from './components/Home/HomeLanding'
import FeaturesList from './components/Features/FeaturesList'
import FeaturesFilm from './components/Features/FeaturesFilm'
import FeaturesLove from './components/Features/FeaturesLove'
import Pricing from './components/Pricing'
import Footer from './components/Footer'

export default {
  name: 'App',
  components: {
    Header, HomeIntro, HomeTemplate, HomeLanding, FeaturesList, FeaturesFilm, FeaturesLove, Pricing, Footer
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
@import url("https://cdn.jsdelivr.net/npm/pixeden-stroke-7-icon@1.2.3/pe-icon-7-stroke/dist/pe-icon-7-stroke.min.css")

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
