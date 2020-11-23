<template>
    <div id="cliente">
        <h1>NOME - {{ cliente.nome }}</h1>
        <hr>
        <p>EMAIL - {{ cliente.email }}</p>
        <p v-show="showIdade">IDADE - {{ cliente.idade }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
        }
    },
    props : {
        cliente : Object,
        showIdade: Boolean
    }
}
</script>

<style scoped>
    #cliente {
        background-color:rgb(82, 49, 114);
        color:rgb(255, 255, 255);
    }
</style>