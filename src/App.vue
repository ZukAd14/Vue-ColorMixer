<template>
  <div id="app">
    <div class="container">

      <!-- header -->
      <app-header />

      <!-- menu -->
      <AppMenu />

      <!-- router view -->
       <slide-fade-animation>
        <router-view />
      </slide-fade-animation>
    </div>
  </div>
</template>

<script>
import './styles/global.scss'
import AppHeader from './components/AppHeader'
import ColorMixin from './components/ColorMixin'
import AppMenu from './components/AppMenu'
import SlideFadeAnimation from './components/shared/SlideFadeAnimation.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    ColorMixin,
    AppMenu,
    SlideFadeAnimation
  }
}
</script>

<style lang="scss">
   @import '@/styles/_variables'
</style>
