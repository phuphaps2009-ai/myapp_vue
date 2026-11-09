<template>
  <v-container style="max-width: 400px;">
    <h1 class="text-center">สมัครสมาชิก</h1>

    <v-text-field v-model="user" label="Username" prepend-icon="mdi-account"></v-text-field>
    <v-text-field v-model="pass" label="Password" type="password" prepend-icon="mdi-lock"></v-text-field>

    <div class="text-center d-flex justify-center ga-2">
      <v-btn color="primary" prepend-icon="mdi-login" @click="check_data">Login</v-btn>
      <v-btn color="red" prepend-icon="mdi-logout" @click="clear_data">Logout</v-btn>
    </div>
    
    <p class="text-center mt-4">{{ result }}</p>
  </v-container>
</template>

<script setup>
import { ref } from 'vue'

const user = ref('')
const pass = ref('')
const result = ref('')

function check_data() {
  if (user.value === 'admin' && pass.value === '1234') {
    result.value = 'เข้าสู่ระบบสำเร็จ'
  } else {
    result.value = 'เข้าสู่ระบบไม่สำเร็จ'
  }
}

function clear_data() {
  user.value = ''
  pass.value = ''
  result.value = ''
}
</script>