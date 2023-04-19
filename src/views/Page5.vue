<template>
    <div class="page5">
        <div class="wlimit">
            <img src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/c5931868a817f2495585f8cf92a4c2aa_8936368115979157998.png" alt="">
            <page5swiper></page5swiper>
        </div>
        
    </div>
</template>

<script setup lang="ts">
import page5swiper from '../components/Page5Swiper.vue'
</script>

<style scoped>
.page5{
    position: absolute;
    width: 100%;
    height: 100%;
   
}
.page5 .wlimit{
    width: 100vw;
    height: 100vh;
    background: url('https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/c71c4defa185a207d7935bd419a8f0f0_4597196462245509440.png') center center no-repeat;
    background-size: cover;
}
.page5 .wlimit img {
    position: absolute;
    width: 40px;
    height: 332px;
    left: 100px;
    top: 30px;
}
</style>