<template>
    <div style="padding:20px;">
        <h1>LSW's Vue Project</h1>

        <div style="display:flex; flex-direction:column; gap:5px;">
            <template v-for="(item, index) in assignments" :key="item.date">
                <!-- 버튼 -->
                <button @click="toggleComponent(index)" :style="{
                    padding: '8px 12px',
                    backgroundColor: selectedIndex === index ? '#42b983' : '#ccc',
                    color: selectedIndex === index ? 'white' : 'black',
                    border: 'none',
                    borderRadius: '4px',
                    cursor: 'pointer',
                    textAlign: 'left'
                }">
                    {{ item.name }}
                </button>

                <!-- 클릭된 버튼 바로 아래에 컴포넌트 렌더링 -->
                <component v-if="selectedIndex === index" :is="item.component" />
            </template>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import day1_0822 from './day1_0822.vue'
import day2_0825 from './day2_0825.vue'
import Day3_0826 from './day3_0826.vue'

const assignments = [
    { date: '2025-08-22', component: day1_0822, name: 'Day1-08/22' },
    { date: '2025-08-25', component: day2_0825, name: 'Day2-08/25' },
    { date: '2025-08-26', component: Day3_0826, name: 'Day3-08/26' },
]

const selectedIndex = ref(null)

function toggleComponent(index) {
    // 같은 버튼 클릭 시 닫기
    selectedIndex.value = selectedIndex.value === index ? null : index
}
</script>
