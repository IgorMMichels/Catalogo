<script setup>
import { ref } from 'vue'
defineProps(['id', 'nome', 'preco', 'imagem', 'categoria'])
import ButtonChild from './ButtonChild.vue'
import { formataPreco } from '@/utils/productUtils'
const mostrarDialog = ref(false)
const emit = defineEmits(['atualizarPreco'])
import ProdutoDialog from './produtos/ProdutoDialog.vue'
function corrigirPreco(id, preco) {
  emit('atualizarPreco', id, preco)
  mostrarDialog.value = false
}
</script>

<template>
  <div class="produto-card">
    <div>
      <img :src="imagem" class="produto-imagem" />
      <h2>{{ nome }}</h2>
      <p>Preço: R$ {{ formataPreco(preco) }}</p>
      <ButtonChild @clique="mostrarDialog = true">Editar</ButtonChild>
      <ProdutoDialog
        v-if="mostrarDialog"
        :nome="nome"
        :id="id"
        :preco="preco"
        :imagem="imagem"
        :categoria="categoria" @fechar="mostrarDialog = false"
        @corrigir-preco="corrigirPreco"
      />
    </div>
  </div>
</template>

<style scoped>
.produto-card {
  border: 1px solid #ccc;
  padding: 24px;
  margin: 16px;
  width: 300px;
}

img {
  width: 100%;
}
</style>
