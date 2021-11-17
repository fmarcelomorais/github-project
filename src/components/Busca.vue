<template>  
  <div class="busca">
    <b-input-group prepend="Usuario">
      <b-form-input></b-form-input>
      <b-input-group-append>
          <b-button variant="success">Buscar</b-button>
      </b-input-group-append>
    </b-input-group>
  </div>  
</template>

<script>

export default {
   name: 'busca',
   data(){
     return{
        busca: ''
     }
   }
}
</script>

<style >
  .busca{
    grid-area: busca;
    background-color: rgb(126, 126, 126);
    padding: 5px;
  }

    
</style>