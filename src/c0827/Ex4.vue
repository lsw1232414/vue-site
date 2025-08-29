<template>
    <div>
        <h2>Computed 1000미만의 숫자 입력</h2>
        <input type="number" v-model.number="score" min="0" max="1000" @input="limitDigits" />
        <p>점수: {{ score }}</p>
        <p>레벨: {{ level }}</p>
    </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const score = ref(0)

// 숫자 입력 제한 (최대 4자리까지만)
function limitDigits(e) {
    let value = e.target.value
    if (value.length > 4) {
        value = value.slice(0, 3) // 앞에서부터 3자리만 유지
        e.target.value = value
    }
    score.value = Number(value) || 0
}

// computed를 활용한 레벨 계산
const level = computed(() => {
    if (score.value >= 800) return '높음'
    if (score.value >= 500) return '보통'
    return '낮음'
})
</script>

<style>
p {
    font-weight: bold;
}
</style>
