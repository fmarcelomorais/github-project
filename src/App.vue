<template>  
<div class="waraper">
    <div class="busca">
      <Busca />   
    </div>
    <div class="usuario">
      <Usuario />
    </div>
    <div class="repositorio">
      <Repositorios />
    </div>
</div>      
</template>

<script>
import Busca from './components/Busca.vue'
import Usuario from './components/Usuario.vue'
import Repositorios from './components/Repositorios.vue'

export default {
  components: {Busca, Usuario, Repositorios }
}
</script>

<style scoped>
  .waraper{
    display: flex;    
    flex-direction: column;
    flex-wrap: wrap;
  }
  .busca{
  
  }
  .usuario{
   display: flex;
  }
  .repositorio{
    display: flex;
    
  }

</style>