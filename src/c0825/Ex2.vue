<script setup>
import { ref } from "vue";

const show = ref(true);
</script>

<template>
    <div>
        <h2>Ex2 - v-if / v-else</h2>
        <button @click="show = !show">누르세요</button>
        <p v-if="show">if 인 상태입니다 </p>
        <p v-else>if가 아닌 else 상태 입니다</p>
    </div>
</template>

<style scoped>
h2 {
    color: darkorange;
}
</style>
