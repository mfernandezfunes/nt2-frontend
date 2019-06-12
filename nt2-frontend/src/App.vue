<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <formPersona msg="Por favor completete los datos de la nueva persona"/>
    

  </div>
</template>

<script>
import formPersona from './components/formPersona.vue'

export default {
  name: 'app',
  components: {
    formPersona
  }
}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
