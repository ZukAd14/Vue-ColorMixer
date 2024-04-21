<template>
    <div class="mixtures">
        <flask-item 
        :key="index"
        v-for="(color, index) in colors"
        :buttonsVisible=false
        :removeButtonVisible=true
        @remove="removeFavColor(index)"
        :amount="100"
        :color="color"
        />
    </div>
</template>

<script>
import FlaskItem from './shared/FlaskItem';
import { mapGetters, mapMutations } from 'vuex'

export default {
    name: 'MyColorList',
    computed: mapGetters({ colors: 'RGBColors' }),
    components: {
        FlaskItem
    },
    methods: {
        ...mapMutations({ removeColor: 'REMOVE_COLOR' }),
        removeFavColor (index) {
            this.removeColor(index)
      
        }
    },
}
</script>

<style lang="scss">
@import '@/styles/_variables'
</style>