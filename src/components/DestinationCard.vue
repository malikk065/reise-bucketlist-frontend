<script setup>
defineProps({
  destination: Object
})
</script>

<template>
  <div class="card">
    <h3>{{ destination.city }}</h3>
    <p>{{ destination.country }}</p>
    <p>Geplant: {{ destination.plannedDate }}</p>
    <p>Budget: {{ destination.budget }} €</p>
    <span v-if="destination.visited">✓ besucht</span>
  </div>
</template>

<style scoped>
.card {
  background: #121b2e;
  color: white;
  border-radius: 16px;
  padding: 16px;
}
</style>