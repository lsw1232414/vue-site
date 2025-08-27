<template>
    <div class="shopping-app" style="padding:20px; max-width:400px;">
        <h3>구매물품 중요도 체크후 목록에 추가하기</h3>

        <!-- 입력 폼 -->
        <div style="margin-bottom:10px;">
            <input v-model="itemName" placeholder="구매할 물품 이름" style="margin-bottom:5px; width:100%; padding:5px;" />
            <input v-model.number="itemCount" type="number" min="1" placeholder="갯수"
                style="margin-bottom:5px; width:100%; padding:5px;" />
            <label>
                중요: <input v-model="isImportant" type="checkbox" />
                {{ isImportant }}
            </label>
        </div>

        <!-- 추가 버튼 -->
        <button @click="addItem" style="margin-bottom:20px;">추가</button>

        <!-- 목록 출력 -->
        <ul>
            <li v-for="(item, index) in shoppingList" :key="index">
                {{ item.name }} - {{ item.count }}개 - 중요: {{ item.important }}
            </li>
        </ul>
    </div>
</template>

<script setup>
import { ref } from "vue"

const itemName = ref("")
const itemCount = ref(1)
const isImportant = ref(false)

const shoppingList = ref([])

const addItem = () => {
    if (!itemName.value || itemCount.value <= 0) return

    shoppingList.value.push({
        name: itemName.value,
        count: itemCount.value,
        important: isImportant.value, // true / false
    })

    // 입력 초기화
    itemName.value = ""
    itemCount.value = 1
    isImportant.value = false
}
</script>
