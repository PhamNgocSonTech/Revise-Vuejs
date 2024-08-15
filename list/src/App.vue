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

const users = ref(
  [
    {
      name: 'Ngoc Son',
      age: 20,
      isActive: true
    },

    {
      name: 'Kim Ngan',
      age: 24,
      isActive: false
    },

    {
      name: 'Phuong Quynh',
      age: 19,
      isActive: false
    },
  ]
)

</script>


<template>
  <div>
    <ul>
      <li v-for="item in shoppingItems" :key="item.name">{{ item.name }} - {{ item.price }}</li>
      <!-- v-for with object -->
      <li v-for="(user, index) in users" :key="user.name">{{ user.name }} : {{ user.isActive ?
        'Active' : 'Deactive' }} (index: {{ index }})
      </li>
    </ul>
    <p v-for="n in 10" :key="n">{{ n }}</p>
  </div>
</template>

<style></style>