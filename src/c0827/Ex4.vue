<template>
  <div>
    <h2>Computed Example - Score Level</h2>
    <input type="number" v-model.number="score" min="0" max="100" placeholder="0~100 점 입력" />
    <p>점수: {{ score }}</p>
    <p>레벨: {{ level }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const score = ref(0)

// computed를 활용한 레벨 계산
const level = computed(() => {
  if (score.value >= 80) return '높음'
  if (score.value >= 50) return '보통'
  return '낮음'
})
</script>

<style>
p {
  font-weight: bold;
}
</style>
