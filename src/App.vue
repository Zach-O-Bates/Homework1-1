<template>
  <div class="p-4 max-w-lg mx-auto">
    <h1 class="text-2xl font-bold mb-4">Order Items</h1>

    <div v-for="item in items" :key="item.name" class="flex justify-between items-center mb-2">
      <span>{{ item.name }}</span>
      <div class="flex items-center gap-2">
        <button @click="decreaseCount(item)" :disabled="item.count === 0" class="bg-gray-300 p-2 rounded">-</button>
        <span>{{ item.count }}</span>
        <button @click="increaseCount(item)" class="bg-blue-500 text-white p-2 rounded">+</button>
      </div>
    </div>

    <button @click="submitOrder" class="bg-green-500 text-white mt-4 p-2 rounded w-full">
      Submit Order
    </button>

    <button @click="praiseTheSun" class="bg-yellow-400 text-black mt-2 p-2 rounded w-full">
      Praise the Sun 🌞
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { name: "Eggs", count: 0 },
        { name: "Tortillas", count: 0 },
        { name: "Chocolate", count: 0 },
      ],
    };
  },
  methods: {
    increaseCount(item) {
      item.count++;
    },
    decreaseCount(item) {
      if (item.count > 0) {
        item.count--;
      }
    },
    submitOrder() {
      alert(`Order Submitted: ${this.items.map(i => `${i.name}: ${i.count}`).join(', ')}`);
    },
    praiseTheSun() {
      alert("🌞 PRAISE THE SUN! 🌞");
    },
  },
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
}
</style>