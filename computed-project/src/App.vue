<script setup>
import { computed, reactive } from 'vue';

const book = reactive({
  name: 'Harry Poster',
  chapters: []
})
const addChapter = () => {
  book.chapters.push('Chapter')
}

// Use Computed Properties
const isPublished = computed(() => book.chapters.length > 0 ? 'Yes' : 'No') 
</script>

<template>
  <div>
    <p id="count">Bookname: {{ book.name }}</p>
    <p id="count">Puslished: {{ isPublished }}</p>
    <button @click="addChapter">add chapter</button>
  </div>
</template>
