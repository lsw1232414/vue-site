<template>
    <div>
        <h3>Ex2: 과일 목록</h3>
        <ul>
            <li v-for="fruit in fruits" :key="fruit">{{ fruit }}</li>
        </ul>
    </div>
</template>

<script setup>
import { ref } from 'vue'
const fruits = ref(['사과', '바나나', '포도'])
</script>
