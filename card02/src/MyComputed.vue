<script setup>
import { ref, computed } from 'vue';

const qty = ref(1)
const price = ref(100)

const total = computed(() => {
    if (qty.value <= 0) return "數量要大於 0"
    if (price.value <= 0) return "單價要大於 0"
    return qty.value * price.value
});
</script>
<template>
    <div class="d-flex align-items-center">
        <h1>計算屬性的實驗 1 </h1>
        <span class="badge text-bg-danger">computed</span>
    </div>


    <div class="input-group mb-1">
        <span class="input-group-text">數量</span>
        <input class="form-control" type="number" v-model.number="qty">
    </div>

    <div class="input-group mb-1">
        <span class="input-group-text">單價</span>
        <input class="form-control" type="number" step="25" v-model.number="price">
    </div>

    <div class="input-group">
        <span class="input-group-text">小計</span>
        <span class="input-group-text flex-fill d-flex justify-content-end text-primary bg-white">{{ total }}</span>
        <!-- <input class=" form-control" type="number" readonly=""> -->
    </div>

</template>
<style scoped></style>