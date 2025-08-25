<script setup>
import { ref } from "vue";

const visible = ref(true);
</script>

<template>
    <div>
        <h2>Ex3 - v-show</h2>
        <button @click="visible = !visible">토글</button>
        <p v-show="visible">이 문장은 v-show로 제어됨 👀</p>
    </div>
</template>

<style scoped>
h2 {
    color: purple;
}
</style>
