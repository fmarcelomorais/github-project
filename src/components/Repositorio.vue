<template>
  <div class="m-3">
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
      <b-link :href="repo.html_url" >{{repo.name}}</b-link>
    </p>
  </b-jumbotron>
</div>
</template>

<script>
import api from "../service/api";
export default {
  name: 'repositorio',
  props: ['user'],
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
        .get(`/users/${this.user}/repos}`)
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