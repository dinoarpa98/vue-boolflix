<template >
<div class="flip-card mx-3 my-3">
  <div class="flip-card-inner">
    <div class="d-flex flip-card-front">
      <img :src="`https://image.tmdb.org/t/p/w342/${poster}`" alt="" class="paneling imgsize ">
    </div>

    <div class="flip-card-back pt-2 p-2 overflow font-size">
      <div class="">Titolo: {{name}}</div>
      <div class="d-flex align-ites-center justify-content-center mt-2">
        <span class="mt-1">Lingua: </span>
        <span class="flag ms-2" :class="(language == 'en') ? 'flag-en' : (language == 'it') ? 'flag-it' : 'flag-unknown' "></span>
      </div>
      
      <div>Trama:</div>
      <span>{{text}}</span>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'SerieCard',
  props: {
    propsArraySerie2: Array,
    poster: String,
    name: String,
    language: String,
    text: String
  }
  }
</script>

<style scoped lang="scss">
  .flag {
    height: 24px;
    width: 24px;
    background-size: contain;
    background-repeat: no-repeat;
    display: inline-block;
  }
 .flag-en {
    background-image: url('../../assets/england.png');
  }
  .flag-it {
    background-image: url('../../assets/italy.png');
  }
  .flag-unknown {
    background-image: url('../../assets/globe.png');
  }
  .imgsize{
    width: 100%;
  }
  
  .paneling{
  width: 225px;
  height: 325px;
}
  .font-size{
    font-size: 12px;
  }
 
//  FLIP
.flip-card {
  background-color: transparent;
  width: 200px;
  height: 300px;
}
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 1.0s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
}
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
  margin-left: 30px;
}
.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}
.flip-card-front {
  background-color: #bbb;
  color: black;
}
.flip-card-back {
  background-color: rgba(0, 0, 0, 0.561);
  color: white;
  transform: rotateY(180deg);
  width: 200px;
}
.overflow{
  overflow-y: scroll;
  ::-webkit-scrollbar {
    display: none;
  }
}

</style>