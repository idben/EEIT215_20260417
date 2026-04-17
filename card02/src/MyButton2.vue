<script setup>
import { computed } from 'vue';

const props = defineProps({
    size: {
        type: String,
        default: "md"
    }
})

const iconClass = computed(() => {
    if (props.size == "sm") return "fa-xs"
    if (props.size == "lg") return "fa-3x"
    return "fa-xl"
});
</script>

<template>
    <!-- 和 MyButton1 不同的是, size 是控制 icon 的大小，不是按鈕的大小 -->
    <button class="btn btn-warning btn-color1 m-1">
        <slot name="icon" :iconClass="iconClass"></slot>
        <slot name="default">按鈕</slot>
    </button>
</template>

<style scoped>
.btn-color1 {
    --bs-btn-color: #fff;
    --bs-btn-bg: #7c3aed;
    --bs-btn-border-color: #7c3aed;
    --bs-btn-hover-color: #fff;
    --bs-btn-hover-bg: #6d28d9;
    --bs-btn-hover-border-color: #6d28d9;
    --bs-btn-active-color: #fff;
    --bs-btn-active-bg: #5b21b6;
    --bs-btn-active-border-color: #5b21b6;
    --bs-btn-disabled-color: #fff;
    --bs-btn-disabled-bg: #c4b5fd;
    --bs-btn-disabled-border-color: #c4b5fd;
}
</style>