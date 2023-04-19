<template>
    <swiper 
    :slidesPerView="1"
    :spaceBetween="30"
    :effect="'fade'" 
    :navigation="{
        prevEl: '.swiper-button-prev',
        nextEl: '.swiper-button-next',
    }" 
    :loop="true"
    :autoplay="{
      delay: 2500,
      disableOnInteraction: false,
    }"
    :fadeEffect="{
         crossFade: true,
    }"
    :modules="modules" class="mySwiper">
        <swiper-slide><img
                src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/ffaffa1f06cedf9c07753fc207a2cc14_7234859343639764052.png" />
        </swiper-slide>
        <swiper-slide><img
                src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/321010199ecb8227ae45bf698aa5db8c_8504296452906820534.png" />
        </swiper-slide>
        <swiper-slide><img 
            src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/80afc525c8b73a5f107adcb92a92191f_4754336978344176815.png" />
        </swiper-slide>
        

    </swiper>
    <!-- 前进后退按钮 -->
   <!-- :src="leftArrowChangeBg" -->
    <div class="swiper-button-prev" >
        <img  class="leftArrowBg" draggable="false" 
        :src="leftArrowChangeBg" alt="" />
    </div>
    <div class="swiper-button-next">
        <img class="rightArrowBg" draggable="false" 
        :src="rightArrowChangeBg" alt="">
    </div>
    
</template>

<script setup lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import "swiper/css/effect-fade";
// import "swiper/css/navigation";
// import "swiper/css/pagination";

// import required modules
import { EffectFade, Navigation, Autoplay} from "swiper";
import { ref } from "vue";
const modules = [EffectFade, Navigation, Autoplay]
const leftArrowChangeBg = ref(
    "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/bf3bb0abcbaf7f4a24e346ba3b11a842_6290742395941952882.png"
);
const rightArrowChangeBg = ref(
    "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/30bf76bc4edde6720ff3c3f061d3e52a_3625245343778810406.png"
);
// const prevSlide = ()=>{
     

// }
</script>

<style scoped>
.swiper {
    width: 100%;
    height: 100%;
    
}

.swiper-slide {
    background-position: center;
    background-size: cover;
    background: transparent !important;
}

.swiper-slide img {
    /* display: block; */
    /* width: 100%; */
    height: 100%;
}
.swiper-button-prev {
    position: absolute;
    left: -120px;
    top: 176px;
    width: 63px;
    height: 62px;
    outline: none;
    /* z-index: 1; */
}
.swiper-button-next{
    position: absolute;
    right: -120px;
    top: 176px;
    width: 63px;
    height: 62px;
    /* outline: none; */
}

/* .swiper-button-prev .leftArrowBg {
    height: 100%;
} */
</style>

