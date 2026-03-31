<script setup>
import { computed } from 'vue';
import { useRoute } from 'vue-router';
import { events } from '@/data/events';

const route = useRoute();

// eslint-disable-next-line @typescript-eslint/no-unused-vars
const evento = computed(() => {
  return events.find(e => e.id === Number(route.params.id));
});
</script>