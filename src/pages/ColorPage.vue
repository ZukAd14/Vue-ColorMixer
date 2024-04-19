<template>
    <div class="page">
      <PageTitle>Color</PageTitle>

      <template v-if="areValuesValid">
      <p>You've picked a great color!</p>

      <FlaskItem
      :size="15"
      :amount="100"
      :buttonsVisible = false
      :style="{ margin: '3rem auto' }"
      :color="mixtureColor"    />

      <button-item
        :size="3"
        :font-size="1.5"
        :movement="0"
        :style="{ margin: 'auto 1rem' }"
        icon="pi pi-share-alt"
        />
        <InputText type="text" v-model='$route.fullPath' />
      </template>

      <template v-else>
      <Message
      :closable="false"
      severity="error">This color is invalid! It's not RGB format...</message>
    </template>

    </div>
  </template>
  
  <script>
  import Message from 'primevue/message';
  import FlaskItem from '../components/shared/FlaskItem.vue';
  import PageTitle from '../components/shared/PageTitle.vue';
  import ButtonItem from '@/components/shared/ButtonItem.vue';
  import InputText from 'primevue/inputtext';
  
  export default {
    name: 'ColorPage',
    components: {
      PageTitle,
      FlaskItem,
      ButtonItem,
      InputText,
      Message
    },
    created() {
        const { red, green, blue } = this.$route.params;
            if (!red || !green || !blue) {
        this.$router.push({ name: 'Home' });
    }
    },

    computed: {
        mixtureColor() {
            const red = parseInt(this.$route.params.red);
            const green = parseInt(this.$route.params.green);
            const blue = parseInt(this.$route.params.blue);
            
            return `rgb(${red}, ${green}, ${blue})`;
        },
        areValuesValid() {
          const red = parseInt(this.$route.params.red);
          const green = parseInt(this.$route.params.green);
          const blue = parseInt(this.$route.params.blue);

          return red >= 0 && red <= 255 && green >= 0 && green <= 255 && blue >= 0 && blue <= 255;
        }
    }
  }
  </script>