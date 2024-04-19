<template>
    <div class="flask" 
    :style="flaskStyle"
    :class="{ 'animate__animated': true, 'animate__shakeY': isAnimated }"
    @animationend="isAnimated = false">

    <!-- decrement btn -->
    <button-item
        v-if="buttonsVisible"
        class="flask__btn flask__btn--left"
        icon="pi pi-angle-double-down"
        @click="zoomIn(); $emit('decrement')" />

    <div
        :class="fillClasses"
        :style="fillStyle" />

    <!-- increment btn -->
    <button-item
        v-if="buttonsVisible"
        class="flask__btn flask__btn--right"
        icon="pi pi-angle-double-up"
        :movement="-0.5"
        @click="zoomIn(); $emit('increment')" />
        </div>
</template>

<script>
import ButtonItem from './ButtonItem.vue'

export default {
  name: 'FlaskItem',
  props: {
    size: {
      type: Number,
      default: 10
    },
    amount: {
      type: Number,
      default: 50
    },
    color: {
      type: String
    },
    variant: {
      type: String
    },
    buttonsVisible: {
      type: Boolean,
      default: true
    }
  },
  data() {
    return {
      isAnimated: false
    };
  },
  computed: {
  flaskStyle () {
    return {
      height: `${this.size}rem`,
      width: `${this.size}rem`
    }
  },

  fillClasses () {
    return [
      'flask__fill',
      (this.variant) && `flask__fill--${this.variant}`
    ]
  },

  fillStyle () {
    const style = { height: this.amount + '%' }

    if (!this.variant) {
      style.backgroundColor = this.color || '#fff'
    }

    return style
    }
    },
    components: {
        ButtonItem
    },
    methods: {
      zoomIn() {
        this.isAnimated = true;
      }
    }
}
</script>

<style lang="scss">
   @import '@/styles/_variables'
</style>