<template>
  <div id="app">
    <h1>Meu primeiro componente</h1>
    <input type="text" v-model="clienteWill.nome">
    <input type="text" v-model="clienteWill.email">
    <Cliente :cliente="clienteWill" :showIdade="true"/>
    <Cliente :cliente="clienteWill" :showIdade="false"/>
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
      }
    }
  },
  components: {
    Cliente
  }
}
</script>

<style>
</style>
