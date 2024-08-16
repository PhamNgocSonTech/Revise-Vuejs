<script setup>
import { ref } from 'vue';

const newTodo = ref('')
const todos = ref(
  [
    {
      id: 1,
      text: 'Learn Vuejs'
    },

    {
      id: 2,
      text: 'Learn JS Basic'
    }
  ]
)

const addTodo = () => {
  if (newTodo.value.trim() === '') return
  const todo = {
    id: todos.value.length + 1,
    text: newTodo.value

  }
  todos.value.push(todo)
}


</script>


<template>
  <input type="text" v-model="newTodo" @keyup.enter="addTodo">
  <button @click="addTodo">Add Todo</button>
  <ul v-for="todo in todos" :key="todo.id">
    <li>{{ todo.text }}</li>
  </ul>
</template>

<style></style>