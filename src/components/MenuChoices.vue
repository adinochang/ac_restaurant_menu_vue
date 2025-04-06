<script setup lang="ts">
import { MenuItem } from '../types/MenuItem'
import menuData from '../data/menu.json'
import { ref, computed } from 'vue'

const items: MenuItem[] = menuData

const searchText = ref('')

const filteredItems = computed(() => {
  return [...items].filter((item) => {
    return item.name.toLowerCase().includes(searchText.value.toLowerCase())
  })
})
</script>

<template>
  <div class="search-container">
    <input v-model="searchText" type="text" class="search-bar" placeholder="Search food..." />
    <button @click="searchText = ''" class="clear-button">Clear</button>
  </div>

  <div class="menu-grid">
    <div v-for="item in filteredItems" :key="item.name" class="food-item">
      <img :src="item.image" :alt="item.name" />
      <h3>{{ item.name }}</h3>
      <p>${{ item.price }}</p>
      <button>Add to Order</button>
    </div>
  </div>
</template>

<style scoped>
.search-container {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

.search-bar {
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 16px;
}

.clear-button {
  padding: 10px 15px;
  background: #888;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  height: 40px;
}

.clear-button:hover {
  background: #c82333;
}

.menu-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 15px;
  max-height: 50vh;
  overflow-y: auto;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background: #fff;
}

.food-item {
  background: white;
  padding: 15px;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.food-item img {
  width: 100%;
  border-radius: 8px;
}

.food-item h3 {
  color: #000;
  margin: 10px 0 5px;
}

.food-item p {
  color: #007bff;
  font-weight: bold;
}

.food-item button {
  background: #007bff;
  color: white;
  border: none;
  padding: 8px 12px;
  border-radius: 4px;
  cursor: pointer;
}

.food-item button:hover {
  background: #0056b3;
}
</style>
