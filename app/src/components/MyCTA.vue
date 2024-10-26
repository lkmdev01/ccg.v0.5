<template>
  <div id="contato" class="bg-white w-full flex justify-center items-center">
    <div
      class="flex flex-col md:flex-row w-11/12 md:w-8/12 my-16 md:my-20 bg-gray-100 border rounded-lg shadow-lg"
    >
      <!-- Seção da imagem -->
      <div
        class="w-full md:w-1/2 bg-form bg-gray-300 rounded-t-lg md:rounded-t-none md:rounded-l-lg"
      ></div>
      <!-- Seção do formulário -->
      <div
        class="w-full md:w-1/2 px-5 md:px-10 py-10 md:py-16 flex justify-center"
      >
        <form
          @submit.prevent="enviarMensagem"
          class="text-gray-800 px-5 w-full"
        >
          <h2 class="text-2xl font-semibold mb-5 text-center md:text-left">
            Fale conosco
          </h2>
          <div class="form-group my-3">
            <p>Nome:</p>
            <input
              v-model="nome"
              type="text"
              placeholder="Digite seu nome"
              class="input input-bordered w-full bg-transparent"
              required
            />
          </div>
          <div class="form-group my-3">
            <p>Email:</p>
            <label
              class="input input-bordered flex items-center gap-2 bg-transparent"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 16 16"
                fill="currentColor"
                class="h-4 w-4 opacity-70"
              >
                <path
                  d="M2.5 3A1.5 1.5 0 0 0 1 4.5v.793c.026.009.051.02.076.032L7.674 8.51c.206.1.446.1.652 0l6.598-3.185A.755.755 0 0 1 15 5.293V4.5A1.5 1.5 0 0 0 13.5 3h-11Z"
                />
                <path
                  d="M15 6.954 8.978 9.86a2.25 2.25 0 0 1-1.956 0L1 6.954V11.5A1.5 1.5 0 0 0 2.5 13h11a1.5 1.5 0 0 0 1.5-1.5V6.954Z"
                />
              </svg>
              <input
                v-model="email"
                type="email"
                class="grow"
                placeholder="Email"
                required
              />
            </label>
          </div>
          <div class="form-group my-3">
            <p>Assunto:</p>
            <select
              v-model="assunto"
              class="select select-bordered w-full bg-transparent"
              required
            >
              <option disabled selected>Sobre o que deseja falar?</option>
              <option>Quero ir à igreja</option>
              <option>Pedido de oração</option>
              <option>Projeto Casas de paz</option>
            </select>
          </div>
          <div class="form-group my-3">
            <p>Mensagem:</p>
            <textarea
              v-model="mensagem"
              class="textarea textarea-bordered w-full bg-transparent"
              placeholder="Sua mensagem"
              required
            ></textarea>
          </div>
          <div class="flex justify-center md:justify-start">
            <button type="submit" class="btn w-full md:w-auto">Enviar</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const nome = ref('')
const email = ref('')
const assunto = ref('')
const mensagem = ref('')

const enviarMensagem = () => {
  const whatsappNumber = '+5513974089412' // Número de destino
  const whatsappLink = `https://api.whatsapp.com/send?phone=${whatsappNumber}&text=Nome: ${encodeURIComponent(nome.value)}%0AEmail: ${encodeURIComponent(email.value)}%0AAssunto: ${encodeURIComponent(assunto.value)}%0AMensagem: ${encodeURIComponent(mensagem.value)}`

  window.open(whatsappLink, '_blank')

  // Limpa os campos após o envio
  nome.value = ''
  email.value = ''
  assunto.value = ''
  mensagem.value = ''
}
</script>

<style scoped>
.bg-form {
  background-image: url('https://i.pinimg.com/736x/38/d4/2e/38d42e8e1c5bd778d5f5746c87bd3256.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

.btn {
  background-color: #2e74d6;
  color: white;
  border: 1px solid #1f4c8d;
  border-radius: 8px;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.btn:hover {
  background-color: #1f4c8d;
}

@media (max-width: 768px) {
  .bg-form {
    height: 200px; /* Ajusta a altura da imagem em telas menores */
  }

  .flex-col {
    flex-direction: column;
  }

  .rounded-t-lg {
    border-radius: 8px 8px 0 0;
  }

  .rounded-l-lg {
    border-radius: 0;
  }
}
</style>
