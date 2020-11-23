<template>
    <div id="cliente">
        <h2>Cliente aqui !!!!</h2>
        <hr>
        <!-- one way data binding : leitura a variavel -->
        <input type="text" :value="nome">

        <!-- two way data binding : atualiza a variavel -->
        <input type="text" v-model="descricao"> 
        <hr>
        <h1>NOME - {{ nome }}</h1>
        <h1>DESCRICAO - {{ descricao }}</h1>
    </div>
</template>

<script>
export default {
    data() {
        return {
            nome : 'Willian Politano',
            numero : '',
            email : '',
            idade : 0,
            descricao : 'LOREM IPSUM'
        }
    }
}
</script>

<style scoped>
    #cliente {
        background-color:rgb(82, 49, 114);
        color:rgb(255, 255, 255);
    }
</style>