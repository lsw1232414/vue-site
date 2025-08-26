<template>
    <div class="fruit-bg">
        <!-- 배경 색 랜덤 변화 -->
        <div class="color-box" @mousemove="colorVal = Math.floor(Math.random() * 360)"
            :style="{ backgroundColor: 'hsl(' + colorVal + ',70%,70%)' }">
            색상값: {{ colorVal }}
        </div>

        <!-- 과일 메뉴 -->
        <div class="menu">
            <ol>
                <li v-for="fruit in fruits" :key="fruit.name" @click="selectedFruit = fruit">
                    {{ fruit.name }}
                </li>
            </ol>

            <!-- 선택한 과일 이미지 -->
            <div class="fruit-info" v-if="selectedFruit">
                <img :src="selectedFruit.img" :alt="selectedFruit.name" />
                <p>이름: {{ selectedFruit.name }}</p>
            </div>
        </div>

        <hr />

        <!-- 전체 과일 목록 반복 출력 -->
        <div class="fruit-list" v-for="fruit in fruits" :key="fruit.name">
            <img :src="fruit.img" :alt="fruit.name" />
            <li>{{ fruit.name }}</li>
        </div>
        <div class="clear"></div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

// 이미지 import
import img_apple from '../assets/img_apple.svg'
import img_banana from '../assets/img_banana.svg'
import img_cherry from '../assets/img_cherry.svg'
import img_grape from '../assets/img_grape.svg'

// 배경 색상
const colorVal = ref(100)

// 과일 데이터
const fruits = ref([
    { name: '사과', img: img_apple },
    { name: '바나나', img: img_banana },
    { name: '체리', img: img_cherry },
    { name: '포도', img: img_grape }
])

// 선택한 과일
const selectedFruit = ref(null)
</script>

<style scoped>
.fruit-bg {
    background-color: gray;
    padding: 20px;
    min-height: 100vh;
}

.color-box {
    padding: 20px;
    text-align: center;
    font-weight: bold;
    border-radius: 8px;
    margin-bottom: 20px;
    transition: background-color 0.2s;
}

.menu {
    display: flex;
    gap: 20px;
    align-items: flex-start;
}

.menu ol {
    list-style: none;
    padding-left: 0;
}

.menu li {
    cursor: pointer;
    margin: 5px 0;
    padding: 5px;
    transition: background-color 0.2s;
}

.menu li:hover {
    background-color: #ffd54f;
}

.fruit-info img {
    width: 100px;
    height: 100px;
    display: block;
    margin-bottom: 5px;
}

.fruit-list {
    width: 100px;
    height: 100px;
    float: left;
    margin: 5px;
    text-align: center;
}

.fruit-list>img {
    width: 50%;
}

.fruit-list>li {
    list-style: none;
    font-weight: bold;
    color: black;
}

.clear {
    clear: both;
}
</style>
