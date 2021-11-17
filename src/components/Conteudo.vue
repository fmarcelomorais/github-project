<template>
<div>
    <h2 class="m-3" v-if="componente === 'Usuarios'" ><b-badge variant="success">Usuarios</b-badge></h2>
    <h2 class="m-3" v-else><b-badge variant="primary">Repositorios</b-badge></h2>
        <br>
    <section fluid>
        <component :is="componente"/>
    </section>

</div>
</template>

<script>
import Repositorio from './Repositorio.vue'
import Usuarios from './Usuarios.vue'
import barramento from '@/barramento'
export default {
    name: 'conteudo',
    components: { Repositorio, Usuarios },
    data(){
        return{
            componente: 'Repositorio'
        }
    },
    created(){
        barramento.$on('UserAll', users => {
            this.componente = users
        })
        barramento.$on('Repositorys', users => {
            this.componente = users
        })
    }
}
</script>

<style>
    .content{
        grid-area: conteudo;    
        display: flex;        
    }

</style>