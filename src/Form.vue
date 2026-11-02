<script setup>
import { ref } from 'vue'

const input_value = ref(0)
const input_ot = ref(0)
const total = ref(0)
const tax = ref(0)

let aaa = 0;
aaa = 20;
function cal_total(){
  total.value = input_value.value + input_ot.value
  tax.value = (3/100)*input_value.value
}

function clear_value(){
  input_value.value = 0
  input_ot.value = 0
  total.value = 0
  tax.value = 0
  
}
</script>

<template>
  <h2>การใช้ Form</h2>
  <input type="number" placeholder="กรอกข้อมูลเงินเดือนของคุณ" v-model="input_value">
  <input type="number" placeholder="กรอกข้อมูล OT ของคุณ" v-model="input_ot">
  <br><br>
  <button @click="cal_total">คำนวณ</button>
  <button @click="clear_value">คืนค่า</button>
  
  <p>เงินเดือนของคุณ : {{ input_value }}</p>
  <p>OT: {{ input_ot }}</p>
  <p>ภาษีหัก ณ ที่ จ่าย 3%: {{ tax }}</p>
  <p>รวม: {{ total}}</p>
</template>