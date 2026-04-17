<script setup>
import MyButton1 from './MyButton1.vue';
import MyComputed from './MyComputed.vue';
import MyComputed2 from './MyComputed2.vue';
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
    <hr>
    <MyComputed2 />
  </div>
</template>
<style scoped></style>