<template>
    <div>
        <h2>5글자 이상 Wachers로 감지하기</h2>
        <input type="text" v-model="userInput" placeholder="글자 5자 이상 감지" />
        <p v-if="status">{{ status }}</p>
    </div>
</template>

<script setup>
import { ref, watch } from 'vue'

const userInput = ref('')
const status = ref('')

// watcher: userInput 값 감시
watch(userInput, (newVal) => {
    if (newVal.length > 5) {
        status.value = '5자 이상 입력되었습니다.'
    } else {
        status.value = ''
    }
})
</script>

<style>
p {
    color: red;
    font-weight: bold;
}
</style>
