<template>
  <q-page class="flex column justify-center items-center q-pa-md" style="min-height: 100vh; background-color: #f9f9f9;">
    <q-avatar rounded size="150px">
      <img src="https://www.organizze.com.br/assets/images/logo-AQ2YPMYN.svg">
    </q-avatar>

    <q-card class="q-pa-lg q-mb-md" style="width: 100%; max-width: 400px;">
      <div class="text-h6 q-mb-md text-center text-accent bold">Acesse sua conta</div>

      <div class="row items-center q-my-sm">
        <q-separator />
      </div>

      <!-- Inputs de Login -->
      <q-input
        outlined
        label="Seu e-mail"
        class="q-mb-sm"
      />

      <!-- Input de Senha com botão para mostrar/esconder -->
      <q-input
        outlined
        :type="showPassword ? 'text' : 'password'"
        v-model="password"
        label="Sua senha"
        class="q-mb-sm"
      >
        <template v-slot:append>
          <q-btn
            flat
            @click="togglePasswordVisibility"
            :label="showPassword ? 'Ocultar' : 'Mostrar'"
            class="q-ml-xs"
          />
        </template>
      </q-input>

      <!-- Esqueci minha senha -->
      <div class="text-right q-mb-md">
        <q-btn flat label="Esqueci minha senha" class="text-primary" />
      </div>

      <!-- Botão Entrar -->
      <q-btn
        color="primary"
        label="Entrar"
        class="q-mb-sm full-width"
      />
    </q-card>

    <!-- Link para Cadastro -->
    <div class="text-center text-bold text-accent">
      Powered By Network To Progress
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue';

const showPassword = ref(false); // Estado para controlar a visibilidade da senha
const password = ref(''); // Estado para armazenar o valor da senha

// Função para alternar a visibilidade da senha
function togglePasswordVisibility() {
  showPassword.value = !showPassword.value;
}

defineOptions({
  name: 'LoginPage'
});
</script>
