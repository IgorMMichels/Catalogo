<script setup>
defineProps(['id', 'nome', 'preco', 'categoria'])
import ButtonChild from './ButtonChild.vue'
defineEmits(['corrigirpreco'])
import { formataPreco } from '@/utils/productUtils'
</script>

<template>
  <li>
    {{ nome }} - {{ formataPreco(preco) }} ({{ categoria }})
    <ButtonChild @clique="$emit('corrigirpreco', id)">Corrigir Preco</ButtonChild>
  </li>
</template>

<style scoped></style>
