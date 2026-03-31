<template>
  <ion-card>
    <ion-card-header>
      <ion-card-title>{{ event.titulo }}</ion-card-title>
    </ion-card-header>

    <ion-card-content>
      <p>{{ event.local }}</p>
      <ion-button @click="$emit('favoritar', event)">
        Favoritar
      </ion-button>
    </ion-card-content>
  </ion-card>
</template>

<script setup>
defineProps(['event']);
defineEmits(['favoritar']);
</script>