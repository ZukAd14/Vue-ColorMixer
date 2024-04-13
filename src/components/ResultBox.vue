<template>
  <div>

    <!-- text between -->
    <p
      v-text="'And the result...'" />

    <!-- mixture effect -->
    <flask-item
      :size="15"
      :amount="100"
      :buttonsVisible = false
      :style="{ margin: '3rem auto' }"
      :color="mixtureEffectFill" />

    <!-- refresh btn -->
    <button-item
      @click="$emit('refresh')"
      :size="4"
      :movement="-0.5"
      :font-size="1.5"
      icon="sync" />

  </div>
</template>

<script>
import ButtonItem from './shared/ButtonItem.vue';
import FlaskItem from './shared/FlaskItem.vue';

export default {
  name: 'ResultsBox',
  props: {
    mixtures: {
      type: Array,
      required: true
    }
  },
  computed: {
    mixtureEffectFill () {
      const [redCol, greenCol, blueCol] = this.mixtures.map(item => Math.floor(item.amount * 2.5))
      return   `rgb(${redCol},${greenCol},${blueCol})`
    }
  },
  components: {
    FlaskItem,
    ButtonItem
  }
}
</script>


