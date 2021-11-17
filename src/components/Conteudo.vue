<template>
<div>
    <h2 class="m-3"><b-badge>Repositorios</b-badge></h2>
        <br>
    <section fluid>
        <Repositorio />
    </section>

</div>
</template>

<script>
import Repositorio from './Repositorio.vue'
export default {
    name: 'conteudo',
    components: { Repositorio }
}
</script>

<style>
    .content{
        grid-area: conteudo;    
        display: flex;        
    }

</style>