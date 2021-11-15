<template>
    <footer class="rodape">
        <p>Desenvolvido por <strong>Marcelo Morais</strong></p>
    </footer>
</template>

<script>
export default {
    name: 'rodape',
}
</script>

<style>
    .rodape{
        grid-area: rodape;
        background-color: rgb(93, 93, 94);
        color: rgb(255, 255, 255);

        display: flex;
        align-items: center;
        justify-content: center;
       
    }
    .rodape p{
        margin: 10px;
    }
</style>