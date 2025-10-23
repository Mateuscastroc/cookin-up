<template>
  <Banner></Banner>
  <Principal>
    <ListaIngredientes></ListaIngredientes>
  </Principal>
  <Rodape></Rodape>
</template>

<script>
  /* Componentes */
  import Banner from './components/Banner.vue'
  import Rodape from './components/Rodape.vue'
  import Principal from './components/Principal.vue'
  import ListaIngredientes from './components/ListaIngredientes.vue'
  export default {
    components: {
      Banner,
      Rodape,
      Principal,
      ListaIngredientes
    },
  /* Dados */
    data() {
      return {
        nome: 'Mateus'
      }
    }
  }
</script>
<style scoped>
</style>
