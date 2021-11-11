<template>
  <div class="usuario">
      <div class="avatar">
          <img :src="user.avatar_url" alt="img"/>
      </div>
      <div class="dados">
          <h2>{{user.name}}</h2>
          <p>{{user.bio}}</p>
      </div>
      <div class="dados1">
          <p>Followers {{user.followers}}</p>
          <p>Following {{user.following}}</p>
          <p>Repositorios {{user.public_repos}}</p>
      </div>

  </div>
</template>

<script>
import api from '../service/api'
export default {
  name: "User",
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

<style scoped>
    .usuario{
        display: flex;
        color: #fff;
    }
    .avatar{
        display: flex;
    }
    .avatar img{
        display: flex;
        border-radius: 50%;
        width: 50%;        
        
    }
    .dados{
        color: #fff;
        display: flex;
        justify-content: flex-start;
    }
</style>