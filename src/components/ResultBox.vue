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

    <p>RGB ({{ mixtures[0].amount * 2.5 }}, {{ mixtures[1].amount * 2.5 }}, {{ mixtures[2].amount * 2.5 }})</p>

    <!-- refresh & info btn -->
    <button-item
      @click="$emit('refresh')"
      :size="4"
      :movement="-0.5"
      :font-size="1.5"
      icon="pi pi-sync" />

    <button-item 
    @click="openModal"
    :size="4"
    :movement="-0.5"
    :font-size="1.5"
    icon="pi pi-question-circle"
    :style="{ margin: '20px' }"/>

    <router-link :to="colorLink">
      <button-item
        :size="4"
        :font-size="1.5"
        icon="pi pi-share-alt"
        />
    </router-link>


    <!-- modal -->
    <fade-animation>
    <modal-item
      v-if="modalVisible"
      @cancel="modalVisible = false">
    
      <template v-slot:header>
        About the app
      </template>

      <template v-slot:body>
        Mix three colors to create the perfect one!
      </template>

      <template v-slot:footer>
        <button-item icon="pi pi-thumbs-up" />
      </template>

    </modal-item>
  </fade-animation>
  </div>
</template>

<script>
import modalMixin from '../mixins/ModalMixin';
import ButtonItem from './shared/ButtonItem.vue';
import FlaskItem from './shared/FlaskItem.vue';
import ModalItem from './shared/modalItem.vue';
import FadeAnimation from './shared/FadeAnimation';

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
    },
    colorLink () {
      const [redCol, greenCol, blueCol] = this.mixtures.map(item => Math.floor(item.amount * 2.5))
      return   `/color/${redCol}/${greenCol}/${blueCol}`
    }
  },
  methods: {
    openModal() {
      this.modalVisible = true;
    }
  },
  components: {
    FlaskItem,
    ButtonItem,
    ModalItem,
    FadeAnimation
  },
  mixins: 
    [modalMixin]
  
}
</script>


