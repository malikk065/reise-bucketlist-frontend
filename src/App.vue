<script setup>
import DestinationList from './components/DestinationList.vue'
</script>

<template>
  <main>
    <h1>Reise-Bucketlist</h1>
    <DestinationList />
  </main>
</template>

<style>
body {
  margin: 0;
  background: #0b1220;
  color: white;
  font-family: system-ui, sans-serif;
}
main {
  max-width: 1000px;
  margin: 0 auto;
  padding: 24px;
}
</style>