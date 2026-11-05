<script setup>
import { ref } from 'vue'
import DestinationCard from './DestinationCard.vue'

const destinations = ref([
  { id: 1, city: 'Lissabon', country: 'Portugal', visited: false, plannedDate: '2027-05-12', budget: 800 },
  { id: 2, city: 'Tokio', country: 'Japan', visited: false, plannedDate: '2027-10-01', budget: 2500 },
  { id: 3, city: 'Kapstadt', country: 'Südafrika', visited: false, plannedDate: null, budget: 1800 },
  { id: 4, city: 'Rom', country: 'Italien', visited: true, plannedDate: '2025-08-20', budget: 600 }
])
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