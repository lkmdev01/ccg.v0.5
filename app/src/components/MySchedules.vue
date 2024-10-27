<template>
  <div id="programacao" class="background-programacao px-5 py-16 md:py-20">
    <h1 class="text-center text-3xl font-bold pb-10 text-white">Programação</h1>
    <div class="max-w-2xl mx-auto flex flex-col gap-3 text-gray-800">
      <div class="collapse collapse-arrow bg-gray-300 rounded-lg">
        <input type="checkbox" id="domingo" class="peer" checked />
        <div class="collapse-title text-xl font-bold" for="domingo">
          Domingo
        </div>
        <div class="collapse-content">
          <p><b>10:12h</b> - Santa ceia | Manhã (Primeiro domingo do mês)</p>
          <p><b>19:12h</b> - Culto da família | Noite</p>
        </div>
      </div>

      <div class="collapse collapse-arrow bg-gray-300 rounded-lg">
        <input type="checkbox" id="terca" class="peer" checked />
        <div class="collapse-title text-xl font-bold" for="terca">Terça</div>
        <div class="collapse-content">
          <p><b>19:12h</b> - Célula | Noite</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.background-programacao {
  background-image: url('/background-programacao.jpg');
}
</style>
