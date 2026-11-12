<script setup>
import { ref } from 'vue'

const Task = ref('')
const Task_List = ref([])
const alert_status = ref(false)

function add_task() {
    if (Task.value != "") {
        Task_List.value.push(Task.value)
        Task.value = ""
    }
    else {
        alert_status.value = true
    }
}
</script>

<template>
    <v-container style="max-width: 500px;" class="text-center">
        <h1>To Do List</h1>
        <v-alert v-if="alert_status"
        text="กรุณาระบุสิ่งที่อยากจะทำ"
        type="warning">
        </v-alert>
        <br>
        <v-text-field
            v-model="Task"
            label="บอกสิ่งที่คุณอยากจะทำ"
            prepend-icon="mdi-playlist-edit">
        </v-text-field>

        <v-btn
            color="green"
            prepend-icon="mdi-plus"
            @click="add_task">
            เพิ่มรายการ
        </v-btn>

        <ol class="text-left">
            <li v-for="(list, index) in Task_List" :key="index">
                <h3>{{ list }}</h3>
                <v-divider></v-divider>
            </li>
        </ol>
    </v-container>
</template>