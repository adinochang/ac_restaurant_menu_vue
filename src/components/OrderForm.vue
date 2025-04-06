<script setup lang="ts">
defineProps({
  newOrder: Object,
})

const orders = []

// const orderSummary = computed(() => {
//   return orders
// })
</script>

<template>
  <h2>Order Summary</h2>
  <table class="summary-table">
    <thead>
      <tr>
        <th>Item</th>
        <th>Price</th>
        <th>Quantity</th>
        <th>Total</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in orders" :key="item.name">
        <td>{{ item.name }}</td>
        <td>{{ item.price }}</td>
        <td><span class="item-decrement">-</span> 1 <span class="item-increment">+</span></td>
        <td>{{ item.price }}</td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td>Total</td>
        <td></td>
        <td></td>
        <td>0.00</td>
        <td></td>
      </tr>
    </tfoot>
  </table>

  <button class="confirm-order">Confirm Order</button>
</template>

<style scoped>
table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

table,
th,
td {
  border: 1px solid #ddd;
}

th,
td {
  padding: 10px;
  text-align: center;
}

th,
tfoot td {
  font-weight: bold;
}

.item-decrement,
.item-increment {
  font-weight: bold;
  font-size: 16px;
  color: #009900;
  margin: 0 15px;
}

.confirm-order {
  width: 100%;
  background: #28a745;
  color: white;
  border: none;
  padding: 10px;
  border-radius: 4px;
  font-size: 16px;
  cursor: pointer;
  margin-top: 20px;
}

.confirm-order:hover {
  background: #218838;
}

h1,
h2 {
  color: #000;
  text-align: center;
}

.summary-table {
  color: #000;
}
</style>
