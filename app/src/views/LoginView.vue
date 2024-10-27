<template>
  <div class="flex justify-center items-center h-screen bg-gray-100">
    <div class="p-8 bg-white shadow-lg rounded-lg w-80">
      <h2 class="text-2xl font-semibold text-gray-800 text-center mb-4">Login</h2>
      <form @submit.prevent="handleLogin">
        <input v-model="username" type="text" placeholder="Username" class="input bg-transparent input-bordered w-full mb-3" />
        <input v-model="password" type="password" placeholder="Password" class="input bg-transparent input-bordered w-full mb-4" />
        <button type="submit" class="btn btn-info w-full">Log in</button>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { useRouter } from 'vue-router';

const username = ref('');
const password = ref('');
const router = useRouter();

const handleLogin = () => {
  if (username.value === 'admin' && password.value === 'password') {
    router.push('/dashboard');
  } else {
    alert('Credenciais inválidas');
  }
};
</script>
