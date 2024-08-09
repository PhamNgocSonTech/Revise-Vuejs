<script setup>
import { computed, reactive, ref } from 'vue';

const book = reactive({
  name: 'Harry Poster',
  chapters: []
})
const addChapter = () => {
  book.chapters.push('Chapter')
}

// Use Computed Properties
const isPublished = computed(() => book.chapters.length > 0 ? 'Yes' : 'No')

const firstName = ref('Nguyen Van')
const lastName = ref('A')

// computed support readonly not write
const changeFullName = () => {
  fullName.value = 'Pham Ngoc,Son'
}

// Correct way
const fullName = computed({
  get() {
    return firstName.value + ' ' + lastName.value
  },
  set(newValue) {
    [firstName.value, lastName.value] = newValue.split(',')
  }
})


</script>


<template>
  <div>
    <p id="count">Bookname: {{ book.name }}</p>
    <p id="count">Puslished: {{ isPublished }}</p>
    <button @click="addChapter">Add Chapter</button>
    <p id="count">Fullname: {{ fullName }}</p>
    <p id="count">First Name: {{ firstName }}</p>
    <p id="count">Last Name: {{ lastName }}</p>
    <button @click="changeFullName">Change Name</button>

  </div>
</template>
