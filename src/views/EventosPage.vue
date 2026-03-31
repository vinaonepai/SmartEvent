<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Eventos</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content>
      <EventCard
        v-for="evento in lista"
        :key="evento.id"
        :event="evento"
        @favoritar="toggleFavorito"
      />
    </ion-content>
  </ion-page>
</template>

<script setup>
import { ref } from 'vue';
import EventCard from '@/components/EventCard.vue';
import { events } from '@/data/events';

const lista = ref(events);

const toggleFavorito = (evento) => {
  evento.favorito = !evento.favorito;
};
</script>