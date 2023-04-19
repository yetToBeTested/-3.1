<template>
  <swiper
    @swiper="onSwiper"
    :direction="'vertical'"
    :slidesPerView="'auto'"
    :spaceBetween="0"
    :mousewheel="true"
    :modules="modules1"
    class="mySwiper"
  >
    <swiper-slide><page1 @MWControl="MWControl"></page1></swiper-slide>
    <swiper-slide><page2></page2></swiper-slide>
    <swiper-slide><page3></page3></swiper-slide>
    <swiper-slide><page4  @playVideo="playVideo"></page4></swiper-slide>
    <swiper-slide><page5></page5></swiper-slide>
    <swiper-slide><page6></page6></swiper-slide>
    <swiper-slide><page7></page7></swiper-slide>
    <swiper-slide class="lastpage"><page8></page8></swiper-slide>
   

  </swiper>
</template>
<script setup lang="ts">
import page1 from './views/Page1.vue'
import page2 from './views/Page2.vue'
import page3 from './views/Page3.vue'
import page4 from './views/Page4.vue'
import page5 from './views/Page5.vue'
import page6 from './views/Page6.vue'
import page7 from './views/Page7.vue'
import page8 from './views/Page8.vue'
import { ref, onMounted } from 'vue'
// import Swiper core and required modules
import { Mousewheel, Pagination, FreeMode, Scrollbar, } from 'swiper';

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles

import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/mousewheel";
// import "swiper/css/bundle";
import "swiper/css/free-mode";
import "swiper/css/scrollbar";


const modules1 = ref([Pagination, Mousewheel, FreeMode, Scrollbar])

var swiperCopy: any = ref()
const onSwiper = ((swiper: any) => {
  swiperCopy = swiper
})

const MWControl = (value: any) => {
  if (!value){
    swiperCopy.disable();
  } 
  else {
    swiperCopy.enable();
  }
};

const playVideo = (value: any) => {
  console.log('valuepapp:', value);
  if (!value) {
    swiperCopy.disable();
  }
   
  else {
    swiperCopy.enable();
  }
};

</script>

<style scoped>
.swiper {
  width: 100%;
  height: 100%;
}
.swiper-slide {
  height: 100vh;
  /* width: 100%; */
  font-size: 30px;
}

.lastpage{
  height: 50vh;
  background-color: black;
}
/* 
.lastpage {
  width: 100%;
  height: 50vh;
  background-color: black;
} */
</style>