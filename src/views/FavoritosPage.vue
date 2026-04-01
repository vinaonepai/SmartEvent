<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button default-href="/home"></ion-back-button>
        </ion-buttons>
        <ion-title>Favoritos</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">
      <div v-if="favoritos.length === 0">
        Nenhum favorito ainda 😢
      </div>

      <EventCard
        v-for="evento in favoritos"
        :key="evento.id"
        :event="evento"
      />

      <ion-button expand="block" router-link="/eventos">
        Voltar para Eventos
      </ion-button>
    </ion-content>
  </ion-page>
</template>

<script setup>
import { computed } from 'vue';
import { events } from '@/data/events';
import EventCard from '@/components/EventCard.vue';

const favoritos = computed(() =>
  events.filter(e => e.favorito)
);
</script>