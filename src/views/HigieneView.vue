<script setup>
import { ref } from 'vue'
import { listaProdutos } from '@/data/products'
const produtos = ref(listaProdutos)
produtos.value = produtos.value.filter((p) => p.categoria === 'Higiene')
import ProdutoCard from '@/components/ProdutoCard.vue'
</script>

<template>
  <div class="container">
    <h1>Alimentos</h1>
    <ProdutoCard
      v-for="produto in produtos"
      :key="produto.id"
      class="produto-card"
      :id="produto.id"
      :nome="produto.nome"
      :preco="produto.preco"
      :imagem="produto.imagem"
      :categoria="produto.categoria"
    >
    </ProdutoCard>
  </div>
</template>

<style scoped></style>
