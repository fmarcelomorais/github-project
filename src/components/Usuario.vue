<template>
  
    <b-card 
      
      :img-src="user.avatar_url"
      img-top      
      style="max-width: 15rem"
      class="mb-2"      >
      <h5><b-link :href="user.html_url">{{user.name}}</b-link></h5>
      <b-card-text>
        
          {{user.bio}}
      </b-card-text>
    </b-card>
 
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
    
</style>