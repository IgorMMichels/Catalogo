<script setup>
import { ref } from 'vue'
import { listaProdutos } from './data/products';
import ProductChild from './components/ProductChild.vue';
import ButtonChild from './components/ButtonChild.vue'
const produtos = ref(listaProdutos);
const alterando = ref(false)
const posicaoProduto = ref(-1)
const preco = ref(0)
function corrigirPreco(idProduto) {
  posicaoProduto.value = produtos.value.findIndex(p => p.id === idProduto);
  preco.value = produtos.value[posicaoProduto.value].preco
  alterando.value=true
}
function salvarPreco() {
  produtos.value[posicaoProduto.value].preco = preco.value
  alterando.value=false
}
</script>

<template>
  <div class="container">
    <h1>Catálogo de Produtos</h1>
    <div>
      <ul>
        <ProductChild v-for="produto in produtos"
        :key="produto.id" :id="produto.id"
        :nome="produto.nome"
        :preco="produto.preco"
        :categoria="produto.categoria"
        @corrigirpreco="corrigirPreco"
        >
        </ProductChild>
      </ul>
    </div>
    <div v-show="alterando">
      <label>Preço</label>
      <input type="number" v-model.number="preco">
      <ButtonChild @clique="salvarPreco(preco)">Salvar</ButtonChild>
    </div>
  </div>
</template>

<style scoped>

</style>
