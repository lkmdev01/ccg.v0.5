<!-- src/components/HelloWorld.vue -->
<template>
  <div class="message-container">
    <h1 class="text-2xl font-bold text-white">{{ message }}</h1>
  </div>
</template>

<script lang="ts">
import { ref, onMounted } from 'vue';
import axios from 'axios';

export default {
    name: 'HelloWorld',
    setup() {
        // Definindo a reatividade com ref
        const message = ref('');

        // Função para buscar a mensagem da API
        const fetchMessage = async () => {
            try {
                const response = await axios.get('http://localhost:8000/api/hello');
                message.value = response.data.message; // Acessando o valor reativo
            } catch (error) {
                console.error('Erro ao conectar à API:', error);
                message.value = 'Erro ao conectar à API';
            }
        };

        // Chamar a função ao montar o componente
        onMounted(fetchMessage);

        // Retornar as variáveis e funções que queremos expor ao template
        return {
            message,
        };
    },
};
</script>

<style scoped>
.message-container {
  text-align: center;
  margin-top: 20px;
}
</style>
