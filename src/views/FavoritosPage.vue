<script setup>
import { computed } from 'vue';
import { events } from '@/data/events';

const favoritos = computed(() =>
  events.filter(e => e.favorito)
);
</script>

<template>
  <div v-if="favoritos.length === 0">
    Nenhum favorito ainda 😢
  </div>
</template>