<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button default-href="/eventos"></ion-back-button>
        </ion-buttons>
        <ion-title>Detalhe</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding" v-if="evento">
      <ion-card>
        <ion-card-header>
          <ion-card-title>{{ evento.titulo }}</ion-card-title>
        </ion-card-header>

        <ion-card-content>
          <p><strong>Local:</strong> {{ evento.local }}</p>

          <ion-button @click="toggleFavorito">
            {{ evento.favorito ? 'Remover dos Favoritos' : 'Favoritar' }}
          </ion-button>
        </ion-card-content>
      </ion-card>
    </ion-content>

    <ion-content v-else>
      <p>Evento não encontrado</p>
    </ion-content>
  </ion-page>
</template>

<script setup>
import { computed } from 'vue';
import { useRoute } from 'vue-router';
import { events } from '@/data/events';

const route = useRoute();

const evento = computed(() => {
  return events.find(e => e.id === Number(route.params.id));
});

const toggleFavorito = () => {
  if (evento.value) {
    evento.value.favorito = !evento.value.favorito;
  }
};
</script>