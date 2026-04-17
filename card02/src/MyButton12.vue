<script setup>
const props = defineProps({
    size: {
        type: String,
        default: "md"
    },
    text: {
        type: String,
        required: true
    },
    icons: {
        type: Array,
        required: true
    }
})

const emits = defineEmits(['alert1']);
</script>

<template>
    <button @click="emits('alert1', '鄭麗文', '還我錢')" class="btn btn-warning btn-color1 m-1" :class="`btn-${props.size}`">
        <i :class="icons"></i>
        {{ props.text }}
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