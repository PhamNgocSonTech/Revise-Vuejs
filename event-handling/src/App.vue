<script setup>
import { ref, reactive } from 'vue';
const count = ref(0)

const greeting = (event) => {
  alert(`Xin Chao ${event.type}`)
}

const sayHi = (name) => {
  alert(`Hi ${name}`)
}

</script>


<template>
  <div>
    <h1>Event Handling</h1>
    <button v-on:click="count++"> Add 1 Unit</button>
    <p>Count: {{ count }}</p>
    <button @:click="greeting"> Greeting</button><br>
    <button @:click="sayHi('Ngoc Son')">say hi Son</button> <br>
    <button @:click="sayHi('Kim Ngan')">say hi Ngan</button>
    <pre>
<code>alert(`Hi ${name}`)
</code>
</pre>

  </div>
</template>

<style></style>