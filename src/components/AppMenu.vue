<template>
    <Menubar :model="items" class="menuBar" />
  </template>
  
  <script>
  import Menubar from 'primevue/menubar'

  export default {
    name: 'AppMenu',
    components: {
        Menubar
    },
    data () {
        return {
        items: [
            {
            label: 'Home',
            icon: 'pi pi-home',
            url: '/'
            },
            {
            label: 'Mixin',
            icon: 'pi pi-sliders-h',
            url: '/mixin'
            },
            {
            label: 'About',
            icon: 'pi pi-info-circle',
            url: '/about'
            },
            {
            label: 'My Colors',
            icon: 'pi pi-star',
            url: '/my-colors'
            }
        ]
        }
    }
  }
  </script>
  
  <style lang="scss" scoped>
    @import '@/styles/_variables'
  </style>