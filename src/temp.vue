<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import page1 from './views/Page1.vue'
import page2 from './views/Page2.vue'
import page3 from './views/Page3.vue'
import page4 from './views/Page4.vue'

import { onBeforeMount, onMounted, ref } from "vue";

import Swiper, { Pagination, Mousewheel } from "swiper";

import 'swiper/css';
import 'swiper/css/pagination';
import 'swiper/css/mousewheel';
// import "../node_modules/swiper/swiper-bundle.min.css";
// import "../node_modules/swiper/swiper-bundle.min.js";
// import "../node_modules/swiper/swiper-bundle.js";

let swiperAble = ref(); //使用swiper方法



//当点击某个部件时禁用swiper（不能滚动到下一页或上一页）
const MWControl = (value: any) => {
    if (!value) swiperAble.value.disable();
    else swiperAble.value.enable();
};


let swiperOptions = ref({}); //swiper设置

onBeforeMount(() => {
    swiperOptions.value = {
        initialSlide: 0, //默认显示第0页
        direction: "vertical", //滑动方向
        speed: 400, //滑动速度
        slidesPerView: "auto", //滑动到贴合边缘
        mousewheel: true, //使用鼠标滚轮
        observer: true, // 监听
        observeParents: true, // 监听
        allowTouchMove: false, //不允许触屏拖动

        //分页器
        // pagination: {
        //     el: ".swiper-pagination",
        //     clickable: true,
        // },
    };
});

onMounted(() => {
    Swiper.use([Pagination, Mousewheel]);
    const mySwiper = new Swiper(".swiperAll", swiperOptions.value); //创建swiper

    swiperAble.value = mySwiper; //复制以使用swiper方法

    // 使用swiper方法
    mySwiper.on("transitionStart", (swiper) => {
        setTimeout(() => { }, 10);
    });
});
</script>

<template>
    <div class="app-body">
        <div class="swiper swiperAll">
            <div class="swiper-wrapper">
                <div class="swiper-slide over">
                    <page1 @MWControl="MWControl"></page1>
                </div>
                <div class="swiper-slide over">
                    <page2></page2>
                </div>
                <div class="swiper-slide over">
                    <!-- <Page3 @playVideo="playVideo"></Page3> -->
                    <page3></page3>
                </div>
                <div class="swiper-slide over">
                    <page4></page4>
                </div>
                <!-- <div class="swiper-slide over">
                <Page5></Page5>
            </div>
            <div class="swiper-slide over">
                <Page6></Page6>
            </div>
            <div class="swiper-slide over">
                <Page7 @canScroll="canScroll"></Page7>
            </div>
            <div class="swiper-slide over footer">
                <Page8></Page8>
            </div> -->
            </div>
            <!-- 如果需要分页器 -->
            <!-- <div class="swiper-pagination"></div> -->
        </div>
    </div>
</template>

<style scoped>
.app-body {
    width: 100vw;
    height: 100vh;
    /* border: 2px solid blue; */
}

.swiper {
    width: 100%;
    height: 100%;
    /* border: 2px solid blue; */
}
</style>



<!-- <template>
  <swiper 
    :modules="modules" 
    :slides-per-view="1" 
    :space-between="50" 
    navigation 
    :pagination="{ clickable: true }"
    :scrollbar="{ draggable: true }" 
    @swiper="onSwiper" 
    @slideChange="onSlideChange">
    <swiper-slide>Slide 1</swiper-slide>
    <swiper-slide>Slide 2</swiper-slide>
    <swiper-slide>Slide 3</swiper-slide>
  </swiper>
</template> -->
<!-- <template>
  <swiper :modules="modules" :slides-per-view="1" :space-between="50" @swiper="onSwiper" @slideChange="onSlideChange">
    <swiper-slide>Slide 1</swiper-slide>
    <swiper-slide>Slide 2</swiper-slide>
    <swiper-slide>Slide 3</swiper-slide>
    ...
  </swiper>
</template>
<script lang="ts" setup>
import { ref } from 'vue'
// import Swiper core and required modules
import { Navigation, Pagination, Scrollbar, A11y } from "swiper";
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";
// Import Swiper styles
import "swiper/css/bundle";

const onSwiper = (swiper: any) => {
    console.log(swiper);
};
const onSlideChange = () => {
  console.log("slide change");
};
let modules=ref([Navigation, Pagination, Scrollbar, A11y])

</script>
<style scoped>
.swiper-slide {
  height: 100vh;
  line-height: 100vh;
  font-size: 30px;
  text-align: center;
  background-color: pink;
}
</style> -->