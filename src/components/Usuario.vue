<template>
  <section class="user">
      <b-card
    :title="user.name"
    :img-src="user.avatar_url"
    img-alt="Image"
    img-top
    tag="article"
    style="max-width: 20rem;"
    class="mb-2"
  >
    <b-card-text>
      {{user.bio}}
    </b-card-text>
    <b-button :href="user.html_url" variant="dark">Meu Perfil no Github</b-button>
    <b-list-group flush>
      <b-list-group-item>Seguidores: <strong>{{user.followers}}</strong></b-list-group-item>
      <b-list-group-item>Seguindo: <strong>{{user.following}}</strong></b-list-group-item>
      <b-list-group-item>Repositorios: <strong>{{user.public_repos}}</strong> </b-list-group-item>
    </b-list-group>
  </b-card>
  </section>
</template>

<script>
import api from '../service/api'
export default {
  name: "user",
  data(){
    return {
       user: {}
    }
  },
  created(){
    this.getUser()
  },
  methods:{
    getUser(){
      api.get('/users/fmarcelomorais').then(res => {
        this.user = res.data;
      }).catch(err => {
        console.log(err)
      })
    }
  }
}
</script>

<style >
    .user{
      grid-area: usuario;

      display: flex;
      
     
    }
</style>