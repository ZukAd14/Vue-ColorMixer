<template>
    <button
        :style="btnStyles"
        class="btn">
      <!-- icon -->
        <span
            v-if="icon"
            :class="`${iconSet} ${icon}`" />

        <!-- text -->
        <span
            v-if="text"
            v-text="text" />
    </button>
  </template>
  
  <script>
  
  export default {
    name: 'ButtonItem',
    props: {
        icon: {
            type: String
        },
        fontSize: {
            type: Number,
            default: 1
        },
        size: {
            type: Number,
            default: 2
        },
        movement: {
            type: Number,
            default: 0.5
        },
        iconSet: {
            type: String,
            default: 'fas'
        },
        text: {
            type: String
        }
    },
    computed: {
        btnStyles () {
            return {
                width: `${this.size}rem`,
                height: `${this.size}rem`,
                fontSize: `${this.fontSize}rem`,
                '--movement': `${this.movement}rem`
            }
        }
    }
  }
  </script>
  
  <style lang="scss" scoped>
    @import '@/styles/_variables'
  </style>