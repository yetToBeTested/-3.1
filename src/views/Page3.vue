<template>
    <div class="page3">
        <div class="wlimit">
            <img class="newWorld" src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/e2685f2daa9175ea47503d97531820ac_6356997034730946416.png" 
            alt="">
            <!-- <page3Swiper></page3Swiper> -->
            <div class="newWorldDetal">
                <page3Swiper></page3Swiper>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import { onUnmounted, onMounted, ref, watch } from "vue";

import page3Swiper from "../components/Page3Swiper.vue";

</script>

<style scoped>
.page3{
    position: relative;
    width: 100%;
    height: 100%;
}
.page3 .wlimit{
    width: 100%;
    height: 100%;
    background: url("https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/e9c6adb1b8fb3bb72763a7f6ca265328_5051941435006923201.jpg")
    center center no-repeat;
    background-size: cover;
}
.page3 .wlimit .newWorld {
    position: absolute;
    width: 40px;
    height: 332px;
    left: 100px;
    top: 30px;
}

.page3 .wlimit .newWorldDetal{
    position: absolute;
    width:712px;
    height: 495px;
    top: 95px;
    left: 327px;
    /* transform: translate(0, -50%); */
    object-fit: contain;
    /* background-color: transparent !important;; */
    /* border: 1px solid red; */
}
</style>