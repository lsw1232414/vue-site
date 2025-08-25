<script setup>
import { ref } from 'vue'

// 불러올 컴포넌트 import
import Ex1 from '../c0825/Ex1.vue'
import Ex2 from '../c0825/Ex2.vue'
import Ex3 from '../c0825/Ex3.vue'
import Ex4 from '../c0825/Ex4.vue'

// 등록할 페이지 컴포넌트 모음
const pages = { Ex1, Ex2, Ex3, Ex4 }

// 현재 보여줄 컴포넌트 상태
const activeComp = ref("Ex1")
</script>

<template>
  <div>
    <button @click="activeComp = 'Ex1'">Bind 바인드</button>
    <button @click="activeComp = 'Ex2'">if_이프</button>
    <button @click="activeComp = 'Ex3'">show_쇼우</button>
    <button @click="activeComp = 'Ex4'">for_포</button>
  </div>

  <div id="comp_view">
    <!-- 동적 컴포넌트 표시 -->
    <KeepAlive>
      <component :is="pages[activeComp]" />
    </KeepAlive>
  </div>
</template>

<style scoped>
button {
  margin: 5px;
  padding: 10px 15px;
  border: none;
  border-radius: 6px;
  background-color: #f0f0f0;
  cursor: pointer;
  transition: background 0.2s;
}

button:hover {
  background-color: #ddd;
}

#comp_view {
  margin-top: 20px;
  padding: 10px;
  border: 1px solid #ddd;
  min-height: 200px;
}
</style>
