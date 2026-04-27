<script setup>
import { ref } from 'vue'
import { listaProdutos } from './data/produtos';
import ProductChild from './components/ProductChild.vue';
const produtos = ref(listaProdutos);
</script>

<template>
  <div class="container">
    <h1>Catálogo de Produtos</h1>
    <div>
      <ul>

      </ul>
    </div>
  </div>
</template>

<style scoped>

</style>
