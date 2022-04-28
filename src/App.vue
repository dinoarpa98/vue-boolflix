<template>
  <div id="app">
    <header>
      <HeaderComp @search="searchMovies"/>
      <MainComp :propsArrayFilm="film" :propsArraySerie="serie"/>
    </header>
  </div>
</template>

<script>
import "bootstrap"
import axios from 'axios';
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
export default {
  //Cambiare il nome con quello del componente creato
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  data(){
    return{
      testoCercato: '',
      filmArray: [],
      film: [],
      serie: [],
    }
  },
  methods: {
    searchMovies( filmCercato ){
      this.testoCercato = filmCercato
      axios.get( `https://api.themoviedb.org/3/search/movie?api_key=4ad83ad18fbd4b0c9488d5ba8b41a927&language=it-IT&page=1&include_adult=false&query=${filmCercato}` )
         .then( ( res )=>{
           console.log( res.data.results );
           this.film = res.data.results
         } )
         .catch( (error) => {
           console.log( error )
         } )
      axios.get( `https://api.themoviedb.org/3/search/tv?api_key=4ad83ad18fbd4b0c9488d5ba8b41a927&language=it-IT&page=1&include_adult=false&query=${filmCercato}` )
          .then( ( res )=>{
            console.log( res.data.results );
            this.serie = res.data.results
          } )
          .catch( (error) => {
            console.log( error )
            console.log(filmCercato)
          } )
      }
    }
  } 
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
</style>