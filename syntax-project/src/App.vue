<script setup>
   const msg = "Hello Son"
   const rawHtml = '<span style="color: red">This should be red.</span>'
   const buttonId = 'btnId'
   const buttonClass = 'btnClass'
   const isButtonDisabled = true
   const objectOfAttrs = {
      id: 'container',
      class: 'wrapper',
      style: {
        color: 'green'
      }
  }
</script>

<template>
  <h1>Son</h1>
  <p>Message: {{ msg }}</p>
  <p>Using v-html directive: <span v-html="rawHtml"></span></p>
  <button v-bind:id="buttonId" :class="buttonClass">Click Here</button>
  <button :disabled="isButtonDisabled">Disabled Button</button>
  <button v-bind="objectOfAttrs">Click Object Attributes</button>

</template>

