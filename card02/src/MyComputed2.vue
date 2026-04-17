<script setup>
import { ref, computed } from 'vue';

const todos = ref([
    { id: 1, text: '學習 Vue', completed: true },
    { id: 2, text: '完成專案', completed: false },
    { id: 3, text: '準備簡報', completed: false },
])

const total = computed(() => todos.value.length);
const completedCount = computed(() => todos.value.filter(todo => todo.completed).length);
const remainingCount = computed(() => todos.value.filter(todo => !todo.completed).length);
</script>
<template>
    <div class="d-flex align-items-center">
        <h1>計算屬性的實驗 2 </h1>
        <span class="badge text-bg-danger">computed</span>
        <span class="badge text-bg-danger ms-1">todo</span>
    </div>
    <ul class="list-group">
        <li v-for="todo in todos" :key="todo.id" class="list-group-item">
            {{ todo.text }}
        </li>
    </ul>
    <div>總計: {{ total }}</div>
    <div>已完成: {{ completedCount }}</div>
    <div>待處理: {{ remainingCount }}</div>

</template>
<style scoped></style>