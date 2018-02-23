<template>
  <div id="app">
    <div v-if="!isLoading">
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
import FeaturesModern from './components/Features/FeaturesModern'
import FeaturesStyle from './components/Features/FeaturesStyle'
import Reviews from './components/Reviews'
import Gallery from './components/Gallery'
import Stages from './components/Stages'
import Content from './components/Content'
import Pricing from './components/Pricing'
import Faq from './components/Faq'
import Team from './components/Team'
import Map from './components/Map'
import Contacts from './components/Contacts'
import Store from './components/Store'
import Footer from './components/Footer'

export default {
  name: 'App',
  data () {
    return {
      isLoading: true
    }
  },
  mounted () {
    this.isLoading = false
  },
  components: {
    Header,
    HomeIntro,
    HomeTemplate,
    HomeLanding,
    FeaturesList,
    FeaturesFilm,
    FeaturesLove,
    FeaturesModern,
    FeaturesStyle,
    Reviews,
    Gallery,
    Stages,
    Content,
    Pricing,
    Faq,
    Team,
    Map,
    Contacts,
    Store,
    Footer
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
