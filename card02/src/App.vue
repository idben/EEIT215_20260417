<script setup>
import MyButton1 from './MyButton1.vue';
import MyComputed from './MyComputed.vue';
import MyComputed2 from './MyComputed2.vue';
import MyButton2 from './MyButton2.vue';
import MyButton3 from './MyButton3.vue';
import MyButton12 from './MyButton12.vue';

const myAlert1 = (text1 = "我", text2 = "好餓") => {
  alert(`${text1}${text2}`);
}

</script>
<template>
  <div class="container">
    <!-- Button trigger modal -->
    <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
      Launch demo modal
    </button>

    <!-- Modal -->
    <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            ...
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </div>
        </div>
      </div>
    </div>

    <hr>

    <MyButton1 size="sm" :aaa="1">
      <template #icon>
        <i class="fa-solid fa-registered"></i>
      </template>
      註冊
    </MyButton1>

    <MyButton1 size="md" :aaa="2">
      登入
      <template #icon>
        <i class="fa-solid fa-arrow-right-to-bracket"></i>
      </template>
    </MyButton1>

    <MyButton1 size="lg" :aaa="3">
      <template #icon>
        <i class="fa-solid fa-star"></i>
      </template>

      <template #default>
        加入我的最愛
      </template>
    </MyButton1>
    <hr>
    <MyComputed />
    <hr class="border border-primary border-2 mt-5">
    <MyComputed2 />

    <hr class="border border-danger border-2 mt-5">

    <MyButton2 size="sm">
      <template #icon="{ iconClass }">
        <i class="fa-solid fa-registered" :class="iconClass"></i>
      </template>
      註冊
    </MyButton2>

    <MyButton2 size="md">
      登入
      <template #icon="{ iconClass }">
        <i class="fa-solid fa-arrow-right-to-bracket" :class="iconClass"></i>
      </template>
    </MyButton2>

    <MyButton2 size="lg">
      <template #icon="{ iconClass }">
        <i class="fa-solid fa-star" :class="iconClass"></i>
      </template>

      <template #default>
        加入我的最愛
      </template>
    </MyButton2>

    <hr class="border border-warning border-2 mt-5">

    <MyButton3 size="md">
      登入
      <template #icon="{ iconClass }">
        <i class="fa-solid fa-arrow-right-to-bracket" :class="iconClass"></i>
      </template>
    </MyButton3>

    <MyButton3 size="lg">
      <template #default>
        加入我的最愛
      </template>
    </MyButton3>


    <hr class="border border-info border-2 mt-5">

    <MyButton12 size="lg" text="唉居" :icons="['fa-brands', 'fa-square-instagram']" @alert1="myAlert1" />

  </div>
</template>
<style scoped></style>