<script setup>
import { ref, watch } from 'vue';

const nome = ref('');

watch(nome, (novo) => {
  console.log('Nome mudou:', novo);
});
</script>

<template>
  <ion-input v-model="nome" placeholder="Seu nome"></ion-input>
</template>