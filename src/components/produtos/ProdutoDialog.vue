<script setup>
import { ref } from 'vue'
defineProps(['nome', 'id', 'preco', 'categoria'])
defineEmits(['corrigirPreco', 'fechar'])
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
      <ButtonChild @clique="$emit('corrigirPreco')">Corrigir Preço</ButtonChild>
      <ButtonChild @clique="$emit('fechar')">Cancelar</ButtonChild>
    </div>
  </div>
</template>

<style scoped>
.produto-dialog {
  border: 1px solid #ccc;
  padding: 16px;
  margin-top: 16px;
}

.overlay {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

</style>
