<template>
    <swiper 
    @swiper="onSwiper"  
    :spaceBetween="30" 
    :effect="'fade'" 
    :fadeEffect="{
    crossFade: false,
    }" 
    :loop=true
    :pagination="pagination" 
    :modules="modules" class="mySwiper">
    
        <swiper-slide>
            <div class="monsterVideo">
                <video ref="" 
                class="monsterVideo1"
                src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/26/a4926264ffdd02a2c52e1281b560f99a_7314909191006900135.mp4"
                autoplay=true 
                loop 
                muted></video>
            </div>
            <img class="text" 
                src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/58b46e908e1dddcc01f8cc13000c474d_8916084097563163728.png"
            alt="">
        </swiper-slide>

        <swiper-slide>
            <div class="monsterVideo">
                <video ref="" class="monsterVideo1"
                    src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/26/828f56d1be90d6e8bb403d338326e6bb_4921388826026954636.mp4"
                    autoplay=true loop muted></video>
            </div>

            <img class="text"
                src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/fe46fa9dc980ff5a56afa682c8a777c9_8016551096094589236.png"
            alt="">
        </swiper-slide>
    </swiper>
    <div class="swiper-pagination5"></div>
    
    <div class="paginations">
        <img :src=item[0]
        @click="paginationClick(0)"
        @mouseover="P5HI(0)" 
        @mouseleave="P5HO(0)" 
        alt="">

        <img :src=item[1]
         @click="paginationClick(1)"
         @mouseover="P5HI(1)" 
        @mouseleave="P5HO(1)" 
        alt="">
    </div>
</template>

<script setup lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import { Pagination, EffectFade } from "swiper";
import { ref } from "vue";
const modules = [Pagination]

const NoClickPagination = ref(["https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/e93c47827d72c7ca41de64337be6b7da_7442467570090845274.png",
                               "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/04865867a7cb486f83a25ca478cc90ad_8041878973233676051.png"                       
])
const ClickPagination = ref(['https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/65bd7a2e3aadf56160c38c05f6a483d1_4985115587357161481.png',
                             'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/fdb644cf1fdfee9faea4cbda4613ca1c_1594927088430841206.png'                    
])

const item = ref<string[]>([ClickPagination.value[0], NoClickPagination.value[1]])
// const item1 = NoClickPagination.value[0]
// const item2 = NoClickPagination.value[1]



const pagination = ref<any>({
    el: '.swiper-pagination5',
    // clickable: true,
    type: 'custom',
    renderCustom: function (swiper: any, current: number, total: number) {
        var paginationHtml = "";
        for (var i = 0; i < total; i++) {
            // 判断是不是激活焦点，是的话添加active类，不是就只添加基本样式类
            if (i === (current - 1)) {
                // console.log("total:", current, total);
            } 
        }
        return paginationHtml;
    }
},) 

var swiperCopy: any = ref()
const onSwiper = ((swiper: any) => {
    swiperCopy = swiper
}) 

const P5HI =(index:number) =>{
    item.value[index] = ClickPagination.value[index]
}
const P5HO = (index: number) => {
    if (!ClickFlag.value[index]){
        item.value[index] = NoClickPagination.value[index]
    }
    
}

const ClickFlag = ref([false,false])
const paginationClick = (index: number) => {
    ClickFlag.value = [false, false]
    ClickFlag.value[index] = true
    swiperCopy.slideTo(index + 1, 10, false);
    paginationActive(index)
}

const paginationActive = (index: number) => {
    item.value[0] = NoClickPagination.value[0]
    item.value[1] = NoClickPagination.value[1]
    item.value[index] = ClickPagination.value[index]
}

</script>

<style scoped>
.swiper-slide .text{
    position: absolute;
    top: 212px;
    left: 940px;
    width: 399px;
    height: 157px;
}
.paginations {
    position: absolute;
    top: 320px;
    left: 170px;
    width: 122px;
    height: 262px;
    align-content: center;
    z-index: 1;
}

.paginations img{
    position: relative;
    width: 106px;
    height: 106px;
    margin-bottom:30px;
}

.monsterVideo {
    position: absolute;
    top: 325px;
    left:635px;
    width: 478px;
    height: 478px;
    border-radius: 50%;
    transform: translate(-50%, -50%);
    overflow: hidden;
}

.monsterVideo1 {
    position: absolute;
    top: 0;
    left: -42%;
    height: 100%;
}
</style>