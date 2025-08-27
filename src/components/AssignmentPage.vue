<template>
    <div class="container">
        <!-- 버튼 영역 -->
        <div class="button-area" :class="{ vertical: selectedIndex !== null }">
            <div v-for="(item, index) in assignments" :key="item.date" class="button-wrapper"
                :class="{ active: selectedIndex === index }" @click="toggleComponent(index)">
                {{ item.name }}
            </div>
        </div>

        <!-- 실행 화면 영역 -->
        <transition name="fade-slide">
            <component v-if="selectedIndex !== null" :is="assignments[selectedIndex].component" class="preview" />
        </transition>
    </div>
</template>

<script setup>
import { ref } from "vue";
import day1_0822 from "./day1_0822.vue";
import day2_0825 from "./day2_0825.vue";
import Day3_0826 from "./day3_0826.vue";
import Day4_0827 from "./day4_0827.vue";

const assignments = [
    { date: "2025-08-22", component: day1_0822, name: "Day1-08/22" },
    { date: "2025-08-25", component: day2_0825, name: "Day2-08/25" },
    { date: "2025-08-26", component: Day3_0826, name: "Day3-08/26" },
    { date: "2025-08-27", component: Day4_0827, name: "Day4-08/27" },
];

const selectedIndex = ref(null);

function toggleComponent(index) {
    selectedIndex.value = selectedIndex.value === index ? null : index;
}
</script>

<style>
.container {
    display: flex;
    height: 100vh;
    padding: 20px;
    gap: 20px;
    box-sizing: border-box;
}

/* 버튼 영역: 초기 가로 5열 */
.button-area {
    display: grid;
    grid-template-columns: repeat(5, 100px);
    gap: 10px;
    transition: all 0.5s ease;
}

/* 선택 시 세로열로 변경 */
.button-area.vertical {
    display: flex;
    flex-direction: column;
    width: 120px;
}

/* 버튼 스타일 */
.button-wrapper {
    width: 100px;
    height: 100px;
    background-color: #ccc;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    text-align: center;
    transition: all 0.3s ease;
}

.button-wrapper.active {
    background-color: #42b983;
    color: white;
    transform: scale(1.05);
}

/* 오른쪽 실행 화면 */
.preview {
    flex: 1;
    background-color: #f5f5f5;
    border-radius: 10px;
    padding: 20px;
    overflow: auto;
}

/* 트랜지션 */
.fade-slide-enter-active,
.fade-slide-leave-active {
    transition: all 0.3s ease;
}

.fade-slide-enter-from,
.fade-slide-leave-to {
    opacity: 0;
    transform: translateX(50px);
}

.fade-slide-enter-to,
.fade-slide-leave-from {
    opacity: 1;
    transform: translateX(0);
}
</style>
