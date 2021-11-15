<template>
    <section class="content m-3">
        <Repositorio />
    </section>
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