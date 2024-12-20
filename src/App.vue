<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <Contador encabezado="Contador primero" :valor="calcular(1, 1)" :esVerdad=muestra1 :valor2="78"/>
  <Contador encabezado="Contador segundo" v-bind:valor="calcular(5, 1)" :esVerdad=muestra2 />
  <button @:click="cambiar(1)">Cambiar Primero</button>
  <button @:click="cambiar(2)">Cambiar Segundo</button>
</template>

<script>
import Contador from './components/Contador.vue'
export default {
  name: 'App',
  components: {
    Contador
  },
  //No deberia programarse en el App
  methods: {
    calcular(a, b) {
      return a + b;
    },
    cambiar(valor) {
      if (valor === 1) {
        this.muestra1 = !this.muestra1;
      } else {
        this.muestra2 = !this.muestra2;
      }
    }
  },
  data() {
    return {
      muestra1: true,
      muestra2: true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
