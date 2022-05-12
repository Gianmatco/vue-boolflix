<template>
   <section>
       sono grislist
       
   </section>
</template>

<script>
import state from '../store.js';
export default {
    name: 'GridList',
    data(){
        return{
            

        }
    },
    methods:{
        leggi(){
            state.search = 'pippo'
            
        }

    }
}
</script>

<style lang="scss">

</style>

