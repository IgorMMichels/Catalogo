<script setup>
import { ref } from 'vue'
import { listaProdutos } from '@/data/products'
const produtos = ref(listaProdutos)
produtos.value = produtos.value.filter((p) => p.categoria === 'Brinquedos')
import ProdutoCard from '@/components/ProdutoCard.vue'
function atualizarPreco(id, novoPreco) {
  const posicao = produtos.value.findIndex((p) => p.id === id)
  produtos.value[posicao].preco = novoPreco
}
</script>

<template>
  <div class="container">
    <h1>Alimentos</h1>
    <ul>
      <ProdutoCard
        v-for="produto in produtos"
        :key="produto.id"
        class="produto-card"
        :id="produto.id"
        :nome="produto.nome"
        :preco="produto.preco"
        :imagem="produto.imagem"
        :categoria="produto.categoria"
        @atualizar-preco="atualizarPreco"
      >
      </ProdutoCard>
    </ul>
  </div>
</template>

<style scoped>
ul {
  display: flex;
}

</style>
