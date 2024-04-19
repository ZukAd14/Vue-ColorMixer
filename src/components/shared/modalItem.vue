<template>

    <div class="fog">
      <div class="modal">
  
        <header>
          <h1>
            <slot name="header" />
          </h1>
        </header>
  
        <div class="modal__body">
          <slot name="body" />
        </div>
  
        <footer class="modal__footer">
          <slot name="footer" />
          <button-item
            icon="pi pi-times"
            @click="$emit('cancel')" />
        </footer>
  
      </div>
    </div>
  </template>
  
  <script>
  import ButtonItem from './ButtonItem'
  
  export default {
    name: 'ModalItem',
    components: {
      ButtonItem
    }
  }
  </script>

  <style scoped lang="scss">
      @import '@/styles/_variables'
  </style>