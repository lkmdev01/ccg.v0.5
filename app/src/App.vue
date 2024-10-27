<script setup lang="ts">
import MyFooter from './components/MyFooter.vue'
import MyHeader from './components/MyHeader.vue'
import { useRoute } from 'vue-router'

const route = useRoute()
</script>

<template>
  <!-- Verifica se a rota atual é diferente de '/login' ou '/dashboard' -->
  <template v-if="['/', '/colaboracoes'].includes(route.path)">
    <MyHeader />
  </template>

  <RouterView />

  <template v-if="['/', '/colaboracoes'].includes(route.path)">
    <MyFooter />
  </template>
</template>

<style scoped>
/* Estilos adicionais, se necessário */
</style>
