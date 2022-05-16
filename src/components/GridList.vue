<template>
   <section>
       <h2>{{title}}</h2>
       <ul>
        <li v-for="item in items" :key="item.id">
          id: {{item.id}}
          titolo originale: {{item.original_title ? item.original_title : item.original_name}} 
          titolo: {{item.title ? item.title : item.name}}
          lingua: {{item.original_language}}
          <!--<img :src="require('./assets/images/'+item.original_language+'.jpg')" alt="">-->
          voto: {{item.vote_average}}
          <img class="img-fluid" :src="image + item.poster_path" alt="">
        </li>
      </ul>
      
       
    </section>
</template>

<script>
import state from '../store.js';
export default {
    name: 'GridList',
    props:{
        items: Array,
        loader: Boolean,
        title: String
    },
    data(){
        return{
            image:'https://image.tmdb.org/t/p/w342'
            

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

