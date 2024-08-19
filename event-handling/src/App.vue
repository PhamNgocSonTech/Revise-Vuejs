<script setup>
import { ref, reactive } from 'vue';
const count = ref(0)

const greeting = (value = 'Xin Chào 2') => {
  alert(`Xin Chao ${value}`)
}

const sayHi = (name) => {
  alert(`Hi ${name}`)
}

const submit = () => {
  alert('Form Submitted')
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
    <!-- <p>Các event lồng nhau xảy ra hiện tượng lan tràn</p>
    <button @:click="sayHi('Xin Chào 1')">
      <button @:click.stop="greeting()">Xin Chào 2</button>
      Xin Chào 1
    </button> <br> -->

    <form @submit.prevent="submit" action="">
      <button type="submit">Submit</button>
    </form>

    <button @:click.self="sayHi('Xin Chào 1')">
      <button @:click.self="greeting()">Xin Chào 2</button>
      Xin Chào 1
    </button> <br>

    <pre>
<code>alert(`Hi ${name}`)
</code>
</pre>

  </div>
</template>

<style></style>