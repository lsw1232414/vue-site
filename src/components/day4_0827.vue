<script setup>
import { ref } from 'vue'

// 불러올 컴포넌트 import
import Ex1 from '../c0827/Ex1.vue'
import Ex2 from '../c0827/Ex2.vue'
import Ex3 from '../c0827/Ex3.vue'
import Ex4 from '../c0827/Ex4.vue'
import Ex5 from '../c0827/Ex5.vue'

// Ex1,
// 등록할 페이지 컴포넌트 모음
const pages = { Ex2, Ex3, Ex4, Ex5 }

// 현재 보여줄 컴포넌트 상태
const activeComp = ref("")
const compBgColor = ref('gray')
</script>

<template>
    <div class="day4bg">
        <div>
            <!-- <button @click="activeComp = 'Ex1';">For</button> -->
            <button @click="activeComp = 'Ex2';">Methods</button>
            <button @click="activeComp = 'Ex3';">Model</button>
            <button @click="activeComp = 'Ex4';">Computed</button>
            <button @click="activeComp = 'Ex5';">Watchers</button>
        </div>

        <div id="comp_view" :style="{ backgroundColor: compBgColor }">
            <KeepAlive>
                <component :is="pages[activeComp]" />
            </KeepAlive>
        </div>
    </div>
</template>

<style scoped>
.day4bg {
    background-color: gray;
}

button {
    margin: 5px;
    padding: 10px 15px;
    border: none;
    border-radius: 6px;
    color: black;
    background-color: #f0f0f0;
    cursor: pointer;
    transition: background 0.2s;
}

button:hover {
    background-color: #ddd;
}

#comp_view {
    margin-top: 20px;
    padding: 10px;
    border: 1px solid #ddd;
    min-height: 200px;
}
</style>
