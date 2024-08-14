<script setup>
import { ref } from 'vue';

const shoppingItems = ref([
  {
    name: "apple",
    price: 8000
  },

  {
    name: "banana",
    price: 10000
  },
])

</script>


<template>
  <div>
    <ul>
      <li v-for="item in shoppingItems" :key="item.name">{{ item.name }} - {{ item.price }}</li>
    </ul>
    <p v-for="n in 10" :key="n">{{ n }}</p>
  </div>
</template>

<style></style>