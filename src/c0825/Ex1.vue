<script setup>
import { ref } from "vue";

const msg = ref("Hello Vue 3!");
</script>

<template>
    <div>
        <h2>Ex1 - Bind 바인드</h2>
        <input v-model="msg" placeholder="메시지 입력" />
        <p>입력값: {{ msg }}</p>
    </div>
</template>

<style scoped>
h2 {
    color: teal;
}
</style>
