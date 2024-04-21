<template>
  <!-- mixtures -->
  <ul class="mixtures">
    <flask-item
      :key="index"
      v-for="(mixture, index) in mixtures"
      :variant="mixture.variant"
      :amount="mixture.amount"
      @increment="$emit('increment', index)"
      @decrement="$emit('decrement', index)" />
  </ul>
</template>

<script>
import { mapGetters } from 'vuex';
import FlaskItem from './shared/FlaskItem.vue';


export default {
  name: 'Mixtures',
  computed: mapGetters({ mixtures: 'Mixtures' }),
  components: {
    FlaskItem
  }
}
</script>

<style scoped lang="scss">
   @import '@/styles/_variables'
</style>