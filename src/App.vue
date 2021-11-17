<template>  
<div id="app">  
    <Busca />   
    <Usuario />
    <Conteudo />
    <Rodape />
</div>      
</template>

<script>
import Busca from './components/Busca.vue'
import Usuario from './components/Usuario.vue'
import Conteudo from './components/Conteudo.vue'
import Rodape from './components/Rodape.vue'


export default {
  components: {Busca, Usuario, Conteudo, Rodape },
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

    grid-auto-rows:  60px 1fr 50px;
    grid-auto-columns: 350px 1fr;
    grid-template-areas: 
      'busca busca'
      'usuario conteudo'
      'usuario conteudo'
      'rodape rodape'
    ;

  }

  @media (max-width: 768px) {
  
  #app{
    grid-auto-rows: 1fr 2fr 1fr;
    grid-auto-columns: 1fr;
    grid-template-areas: 
      'usuario'
      'conteudo'
      'rodape'
    ;
   
  }

}

</style>