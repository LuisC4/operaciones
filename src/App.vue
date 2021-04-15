<template>
  <b-container 
    class="bg-dark w-100 vh-100"
    id="app"
  >
    <Operacion />
  </b-container>
</template>

<script>
import Operacion from './components/Operacion.vue'

export default {
  name: 'App',
  components: {
    Operacion
  }
}
</script>

<style>
body {
  background-color: #343A40;
}
</style>