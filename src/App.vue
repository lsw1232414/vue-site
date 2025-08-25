<template>
  <AssignmentRoom />
</template>

<script setup>
import AssignmentRoom from "./components/AssignmentRoom.vue"
</script>

<style>
html,
body,
#app {
  margin: 0;
  padding: 0;
  width: 100%;
  /* 중요: #app가 화면 전체 높이를 차지 */
  box-sizing: border-box;
  overflow-x: hidden;
  align-items: center;
  justify-content: center;
  display: flex;
}

body {
  background-color: #1e1e2f;
  /* 안전하게 기본 배경 */
  font-family: 'Segoe UI', sans-serif;
}
</style>
