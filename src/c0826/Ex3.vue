<template>
    <div class="ex3bg">
        <h2>할 일 목록</h2>
        <ul>
            <li v-for="(item, index) in todos" :key="index">
                {{ item }}
                <button @click="removeTodo(index)">삭제</button>
            </li>
        </ul>
        <input v-model="newTodo" placeholder="새 할 일 입력">
        <button @click="addTodo">추가</button>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const todos = ref(['Vue 공부', '코드 리뷰', '운동하기'])
const newTodo = ref('')

// 항목 추가
function addTodo() {
    if (newTodo.value.trim() !== '') {
        todos.value.push(newTodo.value.trim())
        newTodo.value = ''
    }
}

// 항목 삭제
function removeTodo(index) {
    todos.value.splice(index, 1)
}
</script>

<style scoped>
.ex3bg {
    background-color: darkblue;
}

ul {
    padding-left: 0;
    list-style: none;
}

li {
    margin: 5px 0;
}

button {
    margin-left: 10px;
}
</style>
