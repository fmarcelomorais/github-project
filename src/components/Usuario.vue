<template>
  <section>   
    <div class="m-3">
    <b-input-group prepend="Usuario">
      <b-form-input v-model="user"></b-form-input>
      <b-input-group-append>
          <b-button variant="success" @click="getUser">Buscar</b-button>
      </b-input-group-append>
    </b-input-group>
   
  </div>      
      <b-card 
        :title="users.name"
        :img-src="users.avatar_url"
        img-alt="Image"
        img-top
        tag="article"
        fluid
       >
    <b-card-text>
      {{users.bio}}
    </b-card-text>
    <b-button :href="users.url" variant="dark">Meu Perfil no Github</b-button>
    <b-list-group flush>
      <b-list-group-item>Seguidores: <strong>{{users.followers}}</strong></b-list-group-item>
      <b-list-group-item>Seguindo: <strong>{{users.following}}</strong></b-list-group-item>
      <b-list-group-item>Repositorios: <strong>{{users.public_repos}}</strong> </b-list-group-item>
    </b-list-group>
  </b-card>
  </section>
</template>

<script>
import api from '../service/api'
import barramento from '@/barramento'

export default {
  name: "user",
  
  data(){
    return {   
      user: '',        
      users: {}       
    }
  },
  /* created(){
    this.getUser()
  }, */
  methods:{
    getUser(){      
    barramento.$emit('dadoUsuario', this.user)
         api.get(`users/${this.user}`).then(res => {
        this.users = res.data;
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