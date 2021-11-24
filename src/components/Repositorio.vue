<template>
  <div class="m-3">   
  <b-alert v-if="repositorios.length < 1" variant="danger" show dismissible>Sem Repositorios</b-alert>
  <div v-else>
    <b-jumbotron 
      bg-variant="dark" 
      text-variant="white" 
      border-variant="dark"
      v-for="repo in repositorios" :key="repo.id"
      >
      
      <template #header>{{repo.name}}</template>

      <template #lead>
        {{repo.description}}
      </template>

      <hr class="my-4">

      <p>
        <b-link :href="repo.html_url" target='_blank'>{{repo.name}}</b-link>
      </p>
    </b-jumbotron>
  </div>

</div>
</template>

<script>
import api from "../service/api";
import barramento from '@/barramento'
export default {
  name: 'repositorios',
  props: ['user'],
  data() {
    return {
      repositorios: {},
      nome: ''
    };
  },
  created() {  
      barramento.$on('dadoUsuario', dado => {
        this.nome = dado
        this.getRepos()
      })
  },
  methods: {
    getRepos() {
      api
        .get(`/users/${this.nome}/repos`)
        .then((res) => {
          this.repositorios = res.data;
        })
        .catch((err) => console.log(err));
    },
  },
};
</script>

<style >
 
</style>