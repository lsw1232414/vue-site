<template>
    <div style="padding:20px;">
        <h1>과제방</h1>

        <!-- 날짜 버튼 -->
        <div style="margin-bottom:20px;">
            <button v-for="item in assignments" :key="item.date" @click="selectedDate = item.date" :style="{
                margin: '5px',
                padding: '8px 12px',
                backgroundColor: selectedDate === item.date ? '#42b983' : '#ccc',
                color: selectedDate === item.date ? 'white' : 'black',
                border: 'none',
                borderRadius: '4px',
                cursor: 'pointer'
            }">
                {{ item.date }}
            </button>
        </div>

        <!-- 선택된 과제 컴포넌트 렌더링 -->
        <component v-if="currentComponent" :is="currentComponent" />
        <div v-else>
            <p>날짜를 선택해주세요.</p>
        </div>
    </div>
</template>

<script setup>
import { ref, computed } from 'vue'

// 날짜별 컴포넌트 import
import day1_0822 from './day1_0822.vue'
import day2_0825 from './day2_0825.vue'
// 필요하면 다른 과제도 import 가능

const assignments = [
    { date: '2025-08-22', component: day1_0822 },
    { date: '2025-08-25', component: day2_0825 },
    // { date: '2025-08-24', component: Assignment0824 }, ...
]

const selectedDate = ref(null)

const currentComponent = computed(() => {
    const found = assignments.find(a => a.date === selectedDate.value)
    return found ? found.component : null
})
</script>
