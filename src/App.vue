<template>
  <div id="app">
    <h1>Meu primeiro componente</h1>
    <cliente/>
  </div>
</template>

<script>
import Cliente from './components/Cliente'
export default {
  name: 'App',
  components: {
    Cliente
  }
}
</script>

<style>
</style>
