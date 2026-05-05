<script setup>
  import { RouterLink } from 'vue-router';
</script>

<template>
  <header>
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/alimentos">Alimentos</RouterLink>
      <RouterLink to="/Brinquedos">Brinquedos</RouterLink>
      <RouterLink to="/acessorios">Acessórios</RouterLink>
      <RouterLink to="/Higiene">Higiene</RouterLink>
    </nav>
  </header>
</template>

<style scoped>
  header {
    position: fixed;
    top: 0; left: 0;
    width: 100%;
    z-index: 100;
    padding: 16px;
    border-bottom: 1px solid #ddd;
    box-sizing: border-box;
  }

  nav {
    display: flex;
    gap: 16px;
  }
</style>
