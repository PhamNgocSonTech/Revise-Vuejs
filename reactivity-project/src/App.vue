<script setup>
import { reactive, ref } from 'vue';

const count = ref(0)

const object = reactive({
  user: {
    age: 18
  },
  count: 1,
  array: [1, 2, 3, 4]
})

const increase = () => count.value++

const change = () => {
  object.user.age++;
  object.count++
  object.array.push(1)
}


</script>

<template>
  <div>
    <p>
      Count Number: {{ count }}
    </p>
    <button @click="increase">Increase Number</button>
    <p>Count User: {{ object.count }}</p>
    <p>Count Age: {{ object.user.age }}</p>
    <p>Push to Array: {{ object.array }}</p>
    <button @click="change">Increase 1 unit</button> <br>
  </div>
</template>
