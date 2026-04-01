<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Eventos</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">
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
import { ref } from 'vue'
import { events } from '../data/events'
import EventCard from '../components/EventCard.vue'

import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue'

const lista = ref(events)

const toggleFavorito = (evento) => {
  evento.favorito = !evento.favorito
}
</script>