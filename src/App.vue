<template>
  <div id="app">
    <h1>Cadastro</h1>
    <small id="nomeErro" v-show="deuErro">O campo nome é obrigatório</small><br>
    <input type="text" placeholder="nome" v-model="nomeField"><br>
    <input type="email" placeholder="email" v-model="emailField"><br>
    <input type="number" placeholder="idade" v-model="idadeField"><br>

    <button class="button is-primary" @click="cadastrarUsuario">Cadastrar</button><br><br>

    <div v-for="cliente in orderClientes" :key="cliente.id">
      <Cliente :cliente="cliente" @meDelete="deletarUsuario($event)"/>
        <input type="text" v-model="cliente.nome">
        <input type="text" v-model="cliente.email">
        <br><br><br>
    </div>
  </div>
</template>

<script>
import _ from 'lodash';
import Cliente from './components/Cliente'
export default {
  name: 'App',
  data(){
    return {
      deuErro: false,
      nomeField: '',
      emailField: '',
      idadeField: 0,
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
  },
  methods: {
    cadastrarUsuario: function() {

      if( this.nomeField.length == '') {
        this.deuErro = true
      } else {
        this.clientes.push({
          nome: this.nomeField,
          email: this.emailField,
          idade: this.idadeField,
          id:Date.now()
        })
        this.deuErro = false
      }
    },
    deletarUsuario: function($event) {
      let id = $event.id
      let novoArray = this.clientes.filter(cliente => cliente.id != id)
      this.clientes = novoArray
    }
  },
  computed: {
    orderClientes: function() {
      return _.orderBy(this.clientes,['nome'],['asc'])
    }
  }
}
</script>

<style>
#nomeErro {
  color: red;
}
</style>
