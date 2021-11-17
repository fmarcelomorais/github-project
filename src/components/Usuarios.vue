<template>
  <div class="usuarios m-3" >
       <b-card 
        :title="users.login"
        :img-src="users.avatar_url"
        img-alt="Image"
        img-top
        tag="article"
        fluid
       >
    <b-card-text>
      
    </b-card-text>
    <b-button :href="users.html_url" variant="dark">Meu Perfil no Github</b-button>
    <b-list-group flush>
      <b-list-group-item>Seguidores: <strong></strong></b-list-group-item>
      <b-list-group-item>Seguindo: <strong></strong></b-list-group-item>
      <b-list-group-item>Repositorios: <strong></strong> </b-list-group-item>
    </b-list-group>
  </b-card>
  </div>
</template>

<script>
import api from "../service/api";
export default {
  data() {
    return {
      users: {},
    };
  },
  created() {
    this.getUser();
  },
  methods: {
    getUser() {
      api
        .get("/user")
        .then((res) => {
          this.users = res.data;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style>
</style>