<script setup lang="ts">
import MenuChoices from './MenuChoices.vue'
</script>

<template>
  <div class="container">
    <h1>Today's Delicious Menu</h1>

    <MenuChoices />
  </div>
</template>

<style scoped>
body {
  font-family: Arial, sans-serif;
  background-color: #f8f9fa;
  color: #333;
  margin: 0;
  padding: 20px;
}

.container {
  max-width: 800px;
  margin: auto;
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

h1,
h2 {
  color: #000;
  text-align: center;
}
</style>
