<template>
    
  <b-navbar type="dark" variant="dark" >
    <b-nav-form >
      <b-form-input class="mr-sm-2" placeholder="Usuario" v-model="busca"></b-form-input>
      <b-button variant="outline-success" class="my-2 my-sm-0" type="submit">Pesquisar</b-button>
    </b-nav-form>
    <h1>{{busca}}</h1>
  </b-navbar>

</template>

<script>

export default {
   
   data(){
     return{
        busca: ''
     }
   }
}
</script>

<style scoped>
    
</style>