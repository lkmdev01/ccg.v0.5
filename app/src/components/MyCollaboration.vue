<template>
  <div
    id="colaboracoes"
    class="flex flex-col justify-center items-center px-5 py-20 bg-azul text-white"
  >
    <h2 class="text-3xl mb-2 font-semibold">SEJA GENEROSO</h2>
    <p class="max-w-2xl text-center">
      A contribuição do cristão deve ser algo leve e prazeroso, quando cremos
      que nossos esforços são para o avanço do reino de Deus na terra. “Pois
      Deus Ama quem dá com alegria” 2CORÍNTIOS 9:7
    </p>
    <button class="btn text-amber-400 mt-5" @click="navigateToColaboracoes">
      Veja as formas de colaborar
    </button>
  </div>
</template>

<script lang="ts" setup>
import { useRouter } from 'vue-router';

const router = useRouter();

const navigateToColaboracoes = () => {
  router.push('/colaboracoes');
};
</script>

<style scoped>
.bg-azul {
  background-image: url('/bg-colabora.png');
  background-size: cover;
  background-repeat: no-repeat;
}
</style>
