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
            },
            {
            label: 'Mixin',
            icon: 'pi pi-sliders-h',
            },
            {
            label: 'About',
            icon: 'pi pi-info-circle',
            }
        ]
        }
    }
  }
  </script>
  
  <style scoped>
  .menuBar {
    border-radius: 1rem;
    box-shadow: 0 20px 40px 0 rgba(107,154,212,.3);
    overflow: hidden;
  }
  </style>