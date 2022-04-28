<template>
   <main class="bg-black p-3 text-white"> 

     <h1 class="ms-2 mb-4">Film</h1>
     <div class="ms-2 d-flex flex-wrap">
      <FilmCard :propsArrayFilm2="propsArrayFilm"
      v-for="( element, index ) in propsArrayFilm"
      :key="index"
      :poster="element.poster_path"
      :title="element.title"
      :ogtitle="element.original_title"
      :language="element.original_language"
      :vote="element.vote_average"
      :overview="element.overview"/>
     </div>

      <h1 class="ms-2 mt-5 mb-4">Serie</h1>
      <div class="ms-2 d-flex flex-wrap">
        <SerieCard :propsArraySerie2="propsArraySerie"
        v-for="( subelement, subindex ) in propsArraySerie"
        :key="`A${subindex}`"
        :poster="subelement.poster_path"
        :name="subelement.name"
        :ogname="subelement.original_name"
        :language="subelement.original_language"
        :vote="subelement.vote_average"
        :overview="subelement.overview"/>
      </div>
      
     

     
   </main>
</template>

<script>
import "bootstrap"
import FilmCard from './MainComps/FilmCard.vue'
import SerieCard from './MainComps/SerieCard.vue'
export default {
  //Cambiare il nome con quello del componente creato
  name: 'MainComp',
  components: {
    FilmCard,
    SerieCard
  },
  props: {
    //ricevere dati tramite props
    propsArrayFilm: Array,
    propsArraySerie: Array
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
 *{
    margin: 0;
    padding: 0;
    box-sizing: inherit;
  }
  .bg-black{
    background-color: #1b1b1b;
  }
</style>