<template>
    <div :class="{'cliente': !isPremium, 'cliente-premium': isPremium}">
        <h1>NOME - {{ cliente.nome }}</h1>
        <hr>
        <p>EMAIL - {{ cliente.email }}</p>
        <p v-show="showIdade">IDADE - {{ cliente.idade }}</p>
        <button @click="mudarCor">Altera cor!</button>
        <button @click="emitirEventoDelete">Deletar</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isPremium: false
        }   
    },
    props : {
        cliente : Object,
        showIdade: Boolean
    },
    methods: {
        mudarCor: function() {
            this.isPremium = !this.isPremium
        },
        emitirEventoDelete: function() {
            this.$emit("meDelete", {id: this.cliente.id, component: this})
        }
    }
}
</script>

<style scoped>
    .cliente {
        background-color:rgb(82, 49, 114);
        color:rgb(255, 255, 255);
    }

    .cliente-premium {
        background-color:rgb(0, 0, 0);
        color:rgb(219, 216, 9);
    }
</style>