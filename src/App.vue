<script setup>
import {ref, reactive  } from 'vue';

const loginStatus = ref(false)
const count = ref(100)
const detail = reactive({
  name: 'ใจ ใขทองคำ',
  cash:99
})
function addCash() {
  detail.cash+=50
}
const student = {
  name: 'สมชายใดี',
  department: 'เทคโนโลยีสารสนเทศ',
  image: 'images.jpg'
}
</script>

<template>
  <button @click="loginStatus = true">เข้าสู่ระบบ</button>
  <button @click="loginStatus = false">ออกจากระบบ</button>
  <p>{{ loginStatus }}</p>
  <p v-if="loginStatus==true">เข้าสู่ระบบเรียบร้อย</p>
  <p v-else>ออกจากระบบเรียบร้อย</p>

  <div v-if="loginStatus == true">
  <p>{{detail.name}} มีเงิน {{detail.cash}} บาท </p>
  <button @click="addCash">เพิ่มเงิน 50 บาท</button>
  <p>จำนวน : {{ count }}</p>
  <button @click="count++">เพิ่มจำนวนอาหาร</button>
  <button @click="count--">ลบจำนวนอาหาร</button>
  <h1>ข้อมูลแมว</h1>
  <p>ชื่อ : {{ student.name }}</p>
  <p>สาขา : {{ student.department}}</p> 
  <img :src="student.image">
  </div>
</template>
