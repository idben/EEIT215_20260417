<script setup>
import { ref, reactive } from 'vue';

const cards = reactive([
    {
        img: "https://images.pexels.com/photos/531844/pexels-photo-531844.jpeg",
        title: "計算機並不一切及時有很多小",
        content: "售價爭取現代批評簡單種子網易持續適應，答應是個趕緊美國禁止控制據說地上具備傳統我一晶片，資料庫，這。"
    },
    {
        img: "https://images.pexels.com/photos/461198/pexels-photo-461198.jpeg",
        title: "常見你們德國要去員工，進入頭髮友情",
        content: "計算機，智能事業機械所需，上班加上消費者，保持願意目前初音資料庫存在區別，這一點小學不多桌面快捷主義不好各個不去，你也註冊三大新臺幣分別只是，協調加強裝備多麼由於，世紀跟我說。"
    },
    {
        img: "https://images.pexels.com/photos/38547/office-freelancer-computer-business-38547.jpeg",
        title: "進攻二手，電視劇，螢",
        content: "自動所需天下尷尬沒人司機貿易分為下載文檔那天訪問女朋友，負責超市希望醫藥也不，德國吃螺。"
    },
    {
        img: "https://images.pexels.com/photos/533325/pexels-photo-533325.jpeg",
        title: "內心重視願意，吃螺絲，現代",
        content: "體驗花園，查找色彩交給，配置必須本月職責之類可愛圍繞，深刻站在從此提高光臨臺中比例書記機構意思，都市馬上國外情節，湖北明顯公共發表遺憾，目光影片一句話唱。"
    }
]);

const num = ref(0);

const nextOne = () => {
    num.value++;
    if (num.value >= cards.length) {
        num.value = 0;
    }
}

const prevOne = () => {
    num.value--;
    if (num.value < 0) {
        num.value = cards.length - 1;
    }
}

</script>
<template>
    <div class="container mt-3">
        <div class="d-flex justify-content-center">
            <div class="card w400px mh300px">
                <img :src="cards[num].img" alt="" class="card-img-top">
                <div class="card-body">
                    <h5 class="card-title">
                        {{ cards[num].title }}
                    </h5>
                    <p>{{ cards[num].content }}</p>
                </div>
                <div class="card-footer">
                    <button @click="prevOne" type="button" class="btn btn-info me-1">上一個</button>
                    <button @click="nextOne" type="button" class="btn btn-info">下一個</button>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped>
.w400px {
    width: 400px;
}

.mh300px {
    min-height: 300px;
}
</style>
