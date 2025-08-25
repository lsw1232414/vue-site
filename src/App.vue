<template>
  <div id="app">
    <!-- 과제방 컴포넌트 렌더링 -->
    <AssignmentPage />
  </div>
</template>

<script setup>
import AssignmentPage from './components/AssignmentPage.vue'
</script>

<style>
/* 전역 스타일 필요하면 여기에 작성 */
body {
  font-family: 'Segoe UI', sans-serif;
  background-color: #f5f5f5;
  margin: 0;
  padding: 0;
}
</style>
