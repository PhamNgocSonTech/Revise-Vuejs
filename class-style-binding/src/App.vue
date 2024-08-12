<script setup>
import { computed, reactive, ref } from 'vue';

const isActive = ref(true)
const hasError = ref(false)
const errorClass = ref('has-error')
const classObject = reactive(({
  active: true,
  'has-error': true
}))

const classObjComputed = computed(() => ({
  active: isActive.value && !hasError.value,
  'has-error': hasError.value
}))

const changeActive = () => {
  isActive.value = !isActive.value
}

// Biding Style

const color = ref('yellow')
const backgroundColor = ref('gray')
const fontSize = ref(20)

const stylesObj = reactive({
  marginTop: '10px',
  border: 'none',
  borderRadius: '6px'
})
</script>


<template>
  <div>
    <button @click="changeActive" class="btn" :class="classObjComputed">{{ isActive ? 'Active' : 'Deactive' }}</button>
    <button @click="changeActive" class="btn" :class="[isActive ? 'active' : '', errorClass]">{{ isActive ? 'Active' :
      'Deactive' }}</button>
  </div>

  <div>
    <button :style="[{
      color,
      backgroundColor,
      fontSize: fontSize + 'px',
      marginTop: marginTop + 'px'
    }, stylesObj]">Binding Style</button>
  </div>
</template>

<style>
.btn {
  border: none;
  background: #ede9fe;
  color: violet;
  padding: 10px 14px;
  border-radius: 6px;
  cursor: pointer;

  &:hover {
    background-color: #c7d2fe;
  }
}

.active {
  background: violet;
  color: #ede9fe;

  &:hover {
    background-color: #818fc8;
  }
}

.has-error {
  background: #ef4444;
  color: #fee2e2;

  &:hover {
    background-color: #f87171;
  }
}
</style>