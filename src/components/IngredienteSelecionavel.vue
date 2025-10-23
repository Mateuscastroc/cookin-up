<template>
    <Tag class="ingrediente" :texto="ingrediente" :ativa="selecionado" @click="aoClicar" />
</template>
<script>
  import Tag from './Tag.vue'
  export default {
    props: {
      ingrediente: {
        type: String,
        required: true
      }
    },
    data() {
      return {
        selecionado: false
      }
    },
    components: {
      Tag
    },
    methods: {
      aoClicar() {
        this.selecionado = !this.selecionado
        if (this.selecionado) {
          this.$emit('adicionarIngrediente', this.ingrediente)
        }
      }
    }
  }
</script>
<style scoped>
  .ingrediente {
    cursor: pointer;	
  }
  
</style>