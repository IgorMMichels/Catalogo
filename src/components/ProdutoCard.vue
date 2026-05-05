<script setup>
import { ref } from 'vue'
defineProps(['id', 'nome', 'preco', 'imagem', 'categoria'])
import ButtonChild from './ButtonChild.vue'
import { formataPreco } from '@/utils/productUtils'
</script>

<template>
    <div class="produto-card">
      <div>
        <img :src="imagem" class="produto-imagem" />
        <h2>{{ nome }}</h2>
        <p>Preço: R$ {{ formataPreco(preco) }}</p>
        <ButtonChild>Editar</ButtonChild>
      </div>
    </div>
</template>

<style scoped>
.produto-card {
  border: 1px solid #ccc;
  padding: 16px;
  margin-bottom: 16px;
  width: 50%;
}

img {
  width: 40%;
}
</style>
