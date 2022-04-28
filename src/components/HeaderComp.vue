<template>
  <header class="d-flex bg-black justify-content-between">
    <div class="">
      <img class="logon" src="../assets/netflix_PNG33.png" alt=""> 
    </div>
    <div class="d-flex">

      <input
      type="text" class="me-2 pt-2 form-control" placeholder="Cerca"
        v-model="testoCercato"
        @keydown.enter="$emit('search', testoCercato)">

      <button type="button" class="btn btn-primary"
        @click="$emit('search', testoCercato)">Cerca</button>

    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComp',
  data() {
    return {
      testoCercato: ''
    };
  }
}
</script>

<style scoped lang="scss">
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  header {
    padding: 20px;
  }
  
  .logon{
    width: 100px;
  }
  
  .bg-black{
    background-color: #1b1b1b88;
  }
  .btn {
    background-color: rgb(255, 0, 0);
    border: rgb(255, 0, 0);
  }
</style>