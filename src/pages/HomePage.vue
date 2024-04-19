<template>
    <page-title>
      <template v-slot>Home</template>
    </page-title>
      <div class="animate__animated animate__bounce animate__delay-2s">
        <message
        :closable="false"
        severity="warn" >Warning! This app is still development</message>
      </div>
    
  </template>
  
  <script>
  import PageTitle from '../components/shared/PageTitle.vue';
  import Message from 'primevue/message'
  export default {
    name: 'HomePage',
  components: {
    PageTitle,
    Message
  }
}
  </script>