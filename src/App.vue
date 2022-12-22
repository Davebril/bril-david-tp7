<template>
  <div class="container-fluid mt-3">
    <h2>TP7 BRIL DAVID</h2>
    
    <div class="jumbotron">
      <br>
      <Navbar />
      <router-view></router-view>

    </div>
  </div>

</template>

<script>
  import Navbar from './componentes/Navbar.vue'

  export default {
    name: 'App',
    components: {
      Navbar
    
    }
  }

</script>

<style scoped >
*{
  background-color: #df9e9e;
}

</style>
