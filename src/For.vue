<script setup>
import { ref } from 'vue'

const student = ref([
  { id: 1, name: 'นายใจ ใช่ทองคำ', score: 100 },
  { id: 2, name: 'นายประสบ พบเจอ', score: 100 },
  { id: 3, name: 'นางนพมาศ รันจวน', score: 100 },
  { id: 4, name: 'นายสาดไป สมาชิก', score: 100 }
])
</script>

<template>
  <h2>รายชื่อนักเรียน</h2>
  <ul>
    <li v-for="list in student" :key="list.id">
      {{ list.name }} | ได้คะแนน {{ list.score }} คะแนน
    </li>
  </ul>
</template>