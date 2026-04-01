<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button default-href="/home"></ion-back-button>
        </ion-buttons>
        <ion-title>Perfil</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">
      <h2>Perfil do Usuário</h2>

      <ion-input
        v-model="nome"
        placeholder="Digite seu nome"
      ></ion-input>

      <p>Nome digitado: {{ nome }}</p>

      <ion-button expand="block" router-link="/eventos">
        Ver Eventos
      </ion-button>
    </ion-content>
  </ion-page>
</template>

<script setup>
import { ref, watch } from 'vue';

const nome = ref('');

watch(nome, (novo) => {
  console.log('Nome mudou:', novo);
});
</script>