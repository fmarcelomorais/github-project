<template>  
<div class="topo">
  <b-navbar toggleable type="dark" variant="dark">
    <b-navbar-brand>
        Api Github
    </b-navbar-brand>
    <div>
   <!-- <b-button @click="usersAll" variant="success">Usuarios</b-button>
   <b-button class="ml-3" @click="Repository" variant="primary">Repositorios</b-button> -->
    </div>
  </b-navbar>
</div>
</template>

<script>
import barramento from '@/barramento'
export default {
   name: 'busca',
   props: ['info'],  
   data(){
     return{
          userAll: 'Usuarios',
          Repositorys: 'Repositorio'
     }
   },
   methods:{
     usersAll(){
       barramento.$emit('UserAll', this.userAll)
     },
     Repository(){
       barramento.$emit('UserAll', this.Repositorys)
     }
     }
}
</script>

<style >
  .topo{
    grid-area: topo;
    background-color: rgb(126, 126, 126);
    padding: 5px;
  }

    
</style>