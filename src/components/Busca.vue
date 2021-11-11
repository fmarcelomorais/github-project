<template>
    <div class="busca">
        <input type="text"> <button>Buscar</button>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    .busca{
       display: flex;
        width: 100%;

    }
    .busca input{
        width: 100%;
        height: 30px;
        font-size: 1.2rem;
        text-transform: lowercase;
        
    }
    .busca button{
        background-color: rgb(19, 214, 248);
        border-radius: 5%;
        border: none;
        width: 10%;
        cursor: pointer;
        margin-left: 5px;
        font-size: 1.0rem;  
    }
    .busca button:hover{
        background-color: rgb(3, 172, 202);
        color: #fff;
    }
</style>