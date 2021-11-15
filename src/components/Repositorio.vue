<template>
  <div class="repository" >
    <b-jumbotron class="m-2 jbt"  
      v-for="repositorio in repositorios" :key="repositorio.id"
        :header="repositorio.name"
        :lead="repositorio.description"
      >
      {{repositorio.name}}
      </b-jumbotron>
  </div>
</template>

<script>
import api from "../service/api";
export default {
  name: 'repositorio',
  data() {
    return {
      repositorios: {},
    };
  },
  created() {
    this.getRepos();
  },
  methods: {
    getRepos() {
      api
        .get("/users/fmarcelomorais/repos")
        .then((res) => {
          this.repositorios = res.data;
        })
        .catch((err) => console.log(err));
    },
  },
};
</script>

<style >
  .repository{
    display: flex;
    
    justify-content:stretch;
    flex-wrap: wrap;    
  }
  .repository .jbt{
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    flex-wrap: wrap;   
    
  }
</style>