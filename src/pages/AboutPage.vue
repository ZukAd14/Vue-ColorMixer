<template>
  <page-title>
    <template v-slot>About</template>
  </page-title>
  <page-title>
    <template v-slot>This app was builit with Vue.js</template>
  </page-title>
    <img 
    src="../assets/logo.png" 
    :class="{ 'animate__animated animate__jackInTheBox': animate }" 
    @click="restartAnimation">
</template>
<script>
import PageTitle from '../components/shared/PageTitle'

export default {
  name: 'AboutPage',
  components: {
    PageTitle
  },
  data() {
    return {
      animate: true
    }
  },
  methods: {
    restartAnimation() {
      this.animate = false
      setTimeout(() => {
        this.animate = true
      }, 10)
    }
  }
}
</script>