<template>
    <div class="page6">
        <div class="wlimit">
            <img src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/6756c91cfe3eb26f2ec33138b7c5d7d6_3556313868834483572.png" alt="">
        <page6swiper></page6swiper>
        </div>
    </div>
</template>

<script setup lang="ts">
import page6swiper from '../components/Page6Swiper.vue'
</script>

<style scoped>
.page6{
    width: 100%;
    height: 100%;
}
.page6 .wlimit {
    width: 100vw;
    height: 100vh;
    background: url("https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/e9c6adb1b8fb3bb72763a7f6ca265328_7152152730301246530.jpg")center center no-repeat;
    background-size: cover;
}

.page6 .wlimit img {
    position: absolute;
    width: 40px;
    height: 332px;
    left: 100px;
    top: 30px;
}
</style>