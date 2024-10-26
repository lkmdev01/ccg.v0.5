<template>
  <div
    id="sobre"
    class="flex flex-col md:flex-row justify-center items-center px-5 py-20 md:py-28 bg-white text-gray-900"
  >
    <!-- Imagem sobre nós -->
    <div class="img-sobre mb-6 md:mb-0 md:pr-10 flex justify-center md:block">
      <img
        src="/sobre.jpg"
        alt="Sobre"
        class="img-fluid rounded-md w-full"
        style="max-width: 500px"
      />
    </div>
    <!-- Texto sobre nós -->
    <div class="content-text text-center md:text-left">
      <h2 class="text-2xl mb-2 font-semibold">A IGREJA QUE COMEÇA EM CASA.</h2>
      <p class="max-w-md">
        A igreja não é apenas um edifício onde as pessoas se reúnem para adorar, mas é a comunidade de crentes que vivem suas vidas em comunhão com Deus. Essa comunidade começa em casa, que é a primeira e fundamental célula da igreja.
        Aqui, valorizamos a comunhão e o ensino da Palavra de Deus de forma simples e fiel. Se você se identificou, gostou da nossa visão, venha nos visitar e conhecer de perto esse projeto.
      </p>
      <!-- Lista de ícones de redes sociais -->
      <ul class="flex justify-center md:justify-start space-x-4 mt-4">
        <li>
          <a
            href="https://www.facebook.com"
            target="_blank"
            rel="noopener noreferrer"
            class="text-gray-600 hover:text-blue-600"
          >
            <i class="fab fa-facebook fa-2x"></i>
          </a>
        </li>
        <li>
          <a
            href="https://www.instagram.com"
            target="_blank"
            rel="noopener noreferrer"
            class="text-gray-600 hover:text-pink-500"
          >
            <i class="fab fa-instagram fa-2x"></i>
          </a>
        </li>
        <li>
          <a
            href="https://www.twitter.com"
            target="_blank"
            rel="noopener noreferrer"
            class="text-gray-600 hover:text-blue-400"
          >
            <i class="fab fa-twitter fa-2x"></i>
          </a>
        </li>
        <li>
          <a
            href="https://www.linkedin.com"
            target="_blank"
            rel="noopener noreferrer"
            class="text-gray-600 hover:text-blue-700"
          >
            <i class="fab fa-linkedin fa-2x"></i>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts" setup>
// Nenhum script adicional necessário para os ícones de redes sociais
</script>

<style scoped>
/* Personalizando a cor do fundo */
.bg-azul {
  background-color: #3d6090;
}

/* Estilo dos ícones */
i {
  font-size: 26px;
  color: #3d6090;
}

/* Responsividade */
</style>
