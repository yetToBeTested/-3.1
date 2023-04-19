<template>
    <!-- <page4Swiper></page4Swiper> -->
    <div class="page4">
        <div class="wlimit">
            <img src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/d88384a1e75d2c93ce8159ef9bd75f0e_4636715245870441785.png"
                alt="">
            <div class="content">
                <page4Swiper @videoId="videoId"></page4Swiper>
            </div>
        
        </div>
    </div>
</template>

<script setup lang="ts">
import page4Swiper from '../components/Page4Swiper.vue'
const emit = defineEmits(["playVideo"]);
const videoId = (value: any) => {
    console.log('valuep4:', value);
    
    emit("playVideo", value);
}

</script>

<style scoped>
.page4 {
    position: relative;
    width: 100vw;
    height: 100vh;
}

.page4 .wlimit {
    width: 100vw;
    height: 100vh;
    background: url("https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/bc6c60df4568561b0ceece4314e04faf_2176544715415915590.png") center center no-repeat;
    background-size: cover;
}

.page4 .wlimit img {
    position: absolute;
    width: 40px;
    height: 332px;
    left: 100px;
    top: 30px;
}

.page4 .wlimit .content{
    width: 100%;
}
</style>