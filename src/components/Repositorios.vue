<template>
  <div>
  <b-jumbotron :header="repo.name" :lead="repo.description"
  v-for="repo in repositorios" :key="repo.id">
    <p>Repositorio {{repo.private ? 'Privado':'Público' }}</p>
    <b-link :href="repo.html_url" variant="primary">Ir ao Repositório</b-link>
  </b-jumbotron>
</div>
</template>

<script>
import api from "../service/api";
export default {
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

<style scoped>

</style>