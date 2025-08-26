<template>
    <div>
        <h3>Ex1: 색상 바꾸기</h3>
        <input type="color" v-model="color" />
        <p :style="{ color }">선택한 색상: {{ color }}</p>
    </div>
</template>

<script setup>
import { ref } from 'vue'
const color = ref('#ff0000')
</script>
