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
const number = 0;
const listStringId = 'a,b,c,d,e,f';
const convertToId = (string) => string.split(',').join('-');
const attributeName = "href";
const url = "https://www.google.com/"
</script>

<template>
  <!-- Text Interpolation -->
  <p>Message: {{ msg }}</p>

  <!-- Raw HTML -->
  <p>Using v-html directive: <span v-html="rawHtml"></span></p>

  <!-- Attribute Bindings -->
  <button v-bind:id="buttonId" :class="buttonClass">Click Here</button>

  <!-- Shorthand -->
  <button :id="buttonId" :class="buttonClass">Button Shorthand Click Here</button>


  <!-- Boolean Attributes -->
  <button :disabled="isButtonDisabled">{{ isButtonDisabled ? 'Disabled' : 'Click Here' }}</button>

  <!-- Dynamically Binding Multiple Attributes -->
  <button v-bind="objectOfAttrs">Click Object Attributes</button>

  <!-- JavaScript Expressions -->
  <button :id="convertToId(listStringId)">Number: {{ number }}</button>

  <!-- Directives -->
  <a v-bind:[attributeName]="url">Click to URL</a>
</template>
