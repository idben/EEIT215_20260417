<script setup>
import { computed, useSlots } from 'vue';

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

const slots = useSlots();

const isEmpty = computed(function () {
    return !slots.icon;
});
</script>

<template>
    <!-- 和 MyButton2 不同的是, 在 template 使用 $slots.icon 判斷父層元件使用元件時有沒有傳入 icon 這個插槽的內容 -->
    <!-- $slots 只能在 template 中用, 在 script 中要用 useSlots() 取出 -->
    <button class="btn btn-warning btn-color1 m-1" :disabled="isEmpty">
        <span v-if="$slots.icon">
            <slot name="icon" :iconClass="iconClass"></slot>
        </span>
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