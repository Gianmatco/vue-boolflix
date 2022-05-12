<template>
  <div id="app">
    <header>
      <h1 class=" display-6">boolflix</h1>
      <search-bar/>

    </header>
    <main>
      <button @click="getMovies">carica</button>
      <ul>
        <li v-for="(movie) in movies" :key="movie.id">
          id: {{movie.id}}
          titolo originale: {{movie.original_title}} 
          titolo: {{movie.title}}
          lingua: {{movie.original_language}}
          voto: {{movie.vote_average}}
        </li>
      </ul>
      <grid-list/>

    </main>
   
  </div>
</template>

<script>
import GridList from './components/GridList.vue'
import SearchBar from './components/SearchBar.vue'
import axios from 'axios'


export default {
  name: 'App',
  components: {
    SearchBar,
    GridList,
  },
  data(){
    return{
      apiKey:'69d52ace6a619430659066d4412ea748',
      apiPath:'https://api.themoviedb.org/3/search/',
      movies:[],
    }
  },
  methods:{
    getMovies(){
      const queryParams = {
        params:{
          api_key: this.apiKey,
          query:'marvel'
        }
      }
      axios.get(this.apiPath+'movie', queryParams).then((res)=>{
        //console.log(res.data.results)
        this.movies = res.data.results;
      })
    }
  }
  //result 
  //id
  //original_title
  //title
  //original_language
  //vote_average
}
</script>

<style lang="scss">
@import './styles/general.scss';
</style>
