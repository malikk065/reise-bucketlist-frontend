<script setup>
import { ref, onMounted } from 'vue'                       // onMounted = wenn die Komponente auf der Seite ist
import DestinationCard from './DestinationCard.vue'

const destinations = ref([])                               // startet leer, Daten kommen vom Backend

onMounted(async () => {                                    // läuft einmal beim Laden der Seite
  const url = import.meta.env.VITE_BACKEND_BASE_URL + '/destinations'  // Adresse aus der .env-Datei
  const response = await fetch(url)                        // GET-Anfrage ans Backend
  destinations.value = await response.json()              // JSON-Antwort in die Liste schreiben
})
</script>

<template>
  <div class="list">
    <DestinationCard
      v-for="d in destinations"
      :key="d.id"
      :destination="d"
    />
  </div>
</template>

<style scoped>
.list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 16px;
}
</style>