<template>
    <div>
        <h2>Methods</h2>
        <div v-for="(task, index) in tasks" :key="index">
            <label>
                <input type="checkbox" v-model="task.checked" />
                {{ getImportance(task) }} - {{ task.name }}
            </label>
        </div>
        <button @click="toggleAll">전체 토글</button>
    </div>
</template>

<script setup>
import { reactive } from 'vue'

const tasks = reactive([
    { name: 'Task 1', checked: false },
    { name: 'Task 2', checked: false },
    { name: 'Task 3', checked: false }
])

function getImportance(task) {
    return task.checked ? '중요' : '보통'
}

function toggleAll() {
    tasks.forEach(task => task.checked = !task.checked)
}
</script>
