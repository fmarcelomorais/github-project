<template>
  <div class="repositorio">
    <div class="card" v-for="repo in repositorios" :key="repo.id">
      <div class="titulo" >
        <h3>{{ repo.name }}</h3>
      </div>
        <span>{{ repo.description }}</span>
    </div>
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
.repositorio{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
.card{
   
    background-color: rgb(76, 0, 255);
    width: 200px;
    height: 200px;
    color: aliceblue;
    margin: 5px;
    
}
</style>