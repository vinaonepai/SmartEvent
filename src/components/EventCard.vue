<template>
  <ion-card>
    <ion-card-header>
      <ion-card-title>{{ event.titulo }}</ion-card-title>
    </ion-card-header>

    <ion-card-content>
      <p>{{ event.local }}</p>

      <ion-button :router-link="`/eventos/${event.id}`">
        Ver Detalhes
      </ion-button>

      <ion-button @click="$emit('favoritar', event)">
        Favoritar
      </ion-button>
    </ion-card-content>
  </ion-card>
</template>

<script setup>
import { IonCard, IonCardHeader, IonCardTitle, IonCardContent, IonButton } from '@ionic/vue'

defineProps(['event'])
defineEmits(['favoritar'])
</script>