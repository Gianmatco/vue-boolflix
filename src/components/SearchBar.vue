<template>
<div>
    <input type="text" v-model="search" @keyup.enter="$emit('performSerch',search)">
    <button @click="cerca">cerca</button>

</div>
    
</template>

<script>

export default {
    name:'SearchBar',
    data(){
        return{
            search:''

        }
    },
    methods:{
        cerca(){
            this.$emit('performSerch',this.search)
            this.search = ''
            
        }

    }
    
}
</script>

<style lang="scss">

</style>