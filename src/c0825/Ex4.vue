<script setup>
const fruits = [" 사과", " 바나나", " 포도", " 오렌지"];
</script>

<template>
    <div>
        <h2>Ex4 - v-for</h2>
        <ul>
            <li v-for="(fruit, i) in fruits" :key="i">{{ fruit }}</li>
        </ul>
    </div>
</template>

<style scoped>
h2 {
    color: green;
}
</style>
