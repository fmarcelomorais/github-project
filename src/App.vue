<template>  
<div id="app">  
    <Topo />  
    <Usuario />
    <Conteudo />
    <Rodape />
</div>      
</template>

<script>
import Topo from './components/Topo.vue'
import Usuario from './components/Usuario.vue'
import Conteudo from './components/Conteudo.vue'
import Rodape from './components/Rodape.vue'


export default {
  components: {Topo, Usuario, Conteudo, Rodape },
  data(){
    return{
      nome: ''
    }
  }
}
</script>

<style >
  *{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
  #app{
    height: 100vh;
    display: grid;

    grid-auto-rows:  60px 2fr 50px;
    grid-auto-columns: 350px 1fr;
    grid-template-areas: 
      'topo topo'
      'usuario conteudo'
      'rodape rodape'
    ;

  }

  @media (max-width: 768px) {
  
  #app{
    grid-auto-rows: 1fr 1fr 2fr 1fr;
    grid-auto-columns: 1fr;
    grid-template-areas: 
      'topo'
      'usuario'
      'conteudo'
      'rodape'
    ;
   
  }

}

</style>