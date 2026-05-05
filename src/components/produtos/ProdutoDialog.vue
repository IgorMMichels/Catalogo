<script setup>
defineProps(['nome', 'id', 'preco', 'categoria'])
import { ref } from 'vue'
import ButtonChild from '../ButtonChild.vue'
import { formataPreco } from '@/utils/productUtils'
const novoPreco = ref(0)
</script>

<template>
  <div class="overlay">
    <div class="produto-dialog">
      <h2>Nome</h2>
      <p>Preço: {{ formataPreco(preco) }}</p>
      <p>Categoria: {{ categoria }}</p>
      <input type="number" v-model.number="novoPreco" />
      <ButtonChild>Corrigir Preço</ButtonChild>
      <ButtonChild></ButtonChild>
    </div>
  </div>
</template>

<style scoped></style>
