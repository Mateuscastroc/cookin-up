<template>
  <span class="subtitulo-lg sua-lista-texto">
    Sua lista
  </span>
  <ul v-if="ingredientes.length !=0" class="ingredientes-sua-lista">
    <li v-for="ingrediente in ingredientes" :key="ingrediente" >
      <Tag @click="aoClicar()" :texto="ingrediente" :ativa="true" />
    </li>
  </ul>
  <p v-else class="lista-vazia">
    <img src="src/assets/logo.svg" alt="Lista vazia">
    Sua lista está vazia.
  </p>
</template>
<script>
  import Tag from './Tag.vue'
  export default {
    props: {
      ingredientes: {
        type:Array,
        required: true
      }
    },
    components: {
      Tag
    },
    methods: {
      aoClicar() {
        this.selecionado = !this.selecionado
        if (this.selecionado) {
          this.$emit('removerIngrediente', this.ingrediente)
        }
      }
    }
  }
</script>
<style scoped>
  .sua-lista-texto {
    color: var(--coral, #F0633C);
    display: block;
    text-align: center;
    margin-bottom: 1.5rem;
  }
  .ingredientes-sua-lista {
    display: flex;
    justify-content: center;
    gap: 1rem 1.5rem;
    flex-wrap: wrap;
  }
</style>