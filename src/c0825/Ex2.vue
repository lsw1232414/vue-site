<script setup>
import { ref } from "vue";

const show = ref(true);
</script>

<template>
    <div>
        <h2>Ex2 - v-if / v-else</h2>
        <button @click="show = !show">토글</button>
        <p v-if="show">보임 </p>
        <p v-else>숨김 </p>
    </div>
</template>

<style scoped>
h2 {
    color: darkorange;
}
</style>
