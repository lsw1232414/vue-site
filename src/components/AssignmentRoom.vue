<template>
  <div class="assignment-room">
    <h1>LSW's Project</h1>
    <p>Vue</p>

    <!-- 1주차 -->
    <section class="week-section">
      <h2 class="week-label">1주차</h2>
      <div class="weekday-header">
        <span>월</span><span>화</span><span>수</span><span>목</span><span>금</span>
      </div>
      <div class="grid">
        <!-- 월~목 빈칸 -->
        <div class="hw empty"></div>
        <div class="hw empty"></div>
        <div class="hw empty"></div>
        <div class="hw empty"></div>
        <!-- 금요일 과제 -->
        <div class="hw">
          <div class="hw-title">
            <span class="day">Day 1 (금)</span>
            <span class="date">8월 22일</span>
          </div>
          <a @click.prevent="openProject('week1/day1')" href="#">프로젝트 보기</a>
        </div>
      </div>
    </section>

    <!-- 2주차 -->
    <section class="week-section">
      <h2 class="week-label">2주차</h2>
      <div class="weekday-header">
        <span>월</span><span>화</span><span>수</span><span>목</span><span>금</span>
      </div>
      <div class="grid">
        <!-- 2주차 월~금 과제 순서대로 -->
        <div v-for="day in week2" :key="day.date" class="hw">
          <div class="hw-title">
            <span class="day">{{ day.label }}</span>
            <span class="date">{{ day.date }}</span>
          </div>
          <a @click.prevent="openProject(day.path)" href="#">프로젝트 보기</a>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from "vue"

const week2 = ref([
  { label: "Day 2 (월)", date: "8월 25일", path: "week2/day2" },
  { label: "Day 3 (화)", date: "8월 26일", path: "week2/day3" },
  { label: "Day 4 (수)", date: "8월 27일", path: "week2/day4" },
  { label: "Day 5 (목)", date: "8월 28일", path: "week2/day5" },
  { label: "Day 6 (금)", date: "8월 29일", path: "week2/day6" },
])

const openProject = (path) => {
  window.open(`/projects/${path}/index.html`, "_blank")
}
</script>

<style scoped>
html,
body,
#app {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  overflow-x: hidden;
}

.assignment-room {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  min-height: 100vh;
  width: 100%;
  background: linear-gradient(135deg, #1e1e2f, #2a2a40);
  color: #ddd;
  box-sizing: border-box;
}

/* 제목 */
h1 {
  font-size: 42px;
  text-align: center;
  margin-bottom: 10px;
  font-weight: 700;
  color: #ffffff;
}

p {
  text-align: center;
  font-size: 18px;
  margin-bottom: 50px;
  color: #cccccc;
}

.week-section {
  width: 100%;
  margin-bottom: 60px;
}

.week-label {
  font-weight: bold;
  font-size: 22px;
  margin-bottom: 14px;
  color: #eeeeee;
  margin-left: 5px;
}

.weekday-header {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  font-weight: bold;
  font-size: 17px;
  text-align: center;
  margin-bottom: 15px;
  color: #cccccc;
}

/* 5칸 그리드 */
.grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 16px;
}

/* 카드 */
.hw {
  background: #1e1e2f;
  border: 1px solid #444;
  padding: 20px;
  text-align: center;
  border-radius: 12px;
  height: 200px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  transition: box-shadow 0.5s ease;
}

.hw:hover {
  box-shadow: 0 0 10px rgba(255, 255, 255, 0.2);
}

/* 카드 제목 */
.hw-title {
  font-weight: bold;
  font-size: 14px;
  margin-bottom: 4px;
  color: #eeeeee;
}

.hw-title .day {
  font-size: 18px;
  display: block;
  font-weight: 600;
  color: #ffffff;
}

.hw-title .date {
  display: block;
  font-size: 14px;
  color: #999999;
}

/* 버튼 */
.hw a {
  display: block;
  width: 100%;
  padding: 10px 0;
  background-color: #3a3a52;
  color: #ddd;
  border: 1px solid #5c5c7a;
  border-radius: 8px;
  text-align: center;
  font-size: 16px;
  font-weight: 600;
  text-decoration: none;
  transition: transform 0.2s, background-color 0.2s;
  box-shadow: 1px 2px 5px rgba(0, 0, 0, 0.2);
}

.hw a:hover {
  background-color: #5865f2;
  transform: scale(1.05);
  color: #fff;
}

/* 빈칸 */
.hw.empty {
  background: #1f1f2c;
  border: 1px dashed #444;
  box-shadow: none;
  pointer-events: none;
}
</style>
