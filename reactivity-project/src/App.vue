<script setup>
import { ref } from 'vue';

const count = ref(0)

const increase = () => count.value++

</script>

<template>
  <div>
    <p>
      Count Number: {{ count }}
    </p>
    <button @click="increase">Increase Number</button>
  </div>
</template>
