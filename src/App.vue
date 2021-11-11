<template>
  <div id="App">
    <div class="topo">
      <Busca />     
    </div>
    <Usuario />
    <Repositorios />
  </div>
</template>

<script>
import Busca from './components/Busca.vue'
import Usuario from './components/Usuario.vue'
import Repositorios from './components/Repositorios.vue'
export default {
  components: {Busca, Usuario, Repositorios}
}
</script>

<style scoped>
  *{
    padding: 0;
    margin: 0;
    box-sizing: border-box;

   
  }
  #App{
    display: flex;
    flex-direction: column;
    justify-content: center;
    background-color: blue;

  }
  .topo{
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: blueviolet;
    padding: 20px;
  }
</style>