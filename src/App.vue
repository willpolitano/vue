<template>
  <div id="app">
    <h1>Meu primeiro componente</h1>

    <div v-for="cliente in clientes" :key="cliente.id">
      <Cliente :cliente="cliente"/>
      <h4>Edição</h4>
        <input type="text" v-model="cliente.nome">
        <input type="text" v-model="cliente.email">
    </div>
  </div>
</template>

<script>
import Cliente from './components/Cliente'
export default {
  name: 'App',
  data(){
    return {
      clienteWill: {
        nome: 'Willian',
        email: 'willianpolitano@gmail.com',
        idade: 21
      },
      clientes: [
        {
          id: 1,
          nome: 'cliente1',
          email: 'cliente1@gmail.com',
          idade: 21
        },
        {
          id: 2,
          nome: 'cliente2',
          email: 'cliente2@gmail.com',
          idade: 22
        },
        {
          id: 3,
          nome: 'cliente3',
          email: 'cliente3@gmail.com',
          idade: 23
        }
      ]
    }
  },
  components: {
    Cliente
  }
}
</script>

<style>
</style>
