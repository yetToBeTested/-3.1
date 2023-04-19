<template>
    <swiper @swiper="onSwiper" :spaceBetween="30" :effect="'fade'" :fadeEffect="{
    crossFade: false,
    }" :loop=true :pagination="pagination" :modules="modules" class="mySwiper">
    
        <swiper-slide>
           <img class="content" src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/7ed1189230096c97cf50e4ba8c8969ba_7946629879694034920.png" 
           alt="">
        </swiper-slide>

        <swiper-slide>
            <img class="content"
                src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/7bca4d0125422998a56bce61e87996e4_2556108400450633928.png"
                alt="">
        </swiper-slide>
        <swiper-slide>
            <img class="content" src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/538e32ce6061eef3fcb2cbed85fb4bd4_5881894550695429827.png" 
            alt="">
        </swiper-slide>

        <swiper-slide>
            <img class="content" src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/922c136b588da821fab6bf91f618dd3a_4610305472830750129.png" 
            alt="">
        </swiper-slide>
    </swiper>
    <div class="swiper-pagination5"></div>
    
    <div class="line">
        <img src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/459a6d76235e4d017c9fb0056eb6b7df_4825382880616669471.png" alt="">
    </div>

    <div class="paginations">
        <img :src=item[0]
         @mouseover="P6HI(0)" 
         @mouseleave="P6HO(0)"
        @click="paginationClick(0)" alt="">
        <img :src=item[1]
            @click="paginationClick(1)" alt="">
        <img :src=item[2]
            @click="paginationClick(2)" alt="">
        <img :src=item[3]
            @click="paginationClick(3)" alt="">
    </div>
</template>

<script setup lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import { Pagination, EffectFade } from "swiper";
import { ref } from "vue";
const modules = [Pagination]

const ClickPagination = ref(['https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/32ead1aae2e7355c98fec7bd184854a5_3800692510629528364.png',
                            'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/dae1f27ba09d776a4db670af2a83a09e_7614592235591423711.png',
                            'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/6d533d3642701588836c403f140878f2_7088843679621528115.png',
                            'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/42d1174d411ed47b50fa48be9492830b_6246282135478031486.png'
])
const NoClickPagination = ref(['https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/559dfb7d87a527f11eae3e250febea6e_7708099465538725906.png',
                                'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/4c4009914a151d6e1726856542940821_1740160534721080850.png',
                                'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/735dadcbb4ea7a8428147d3806b3b5f0_6877776947729540757.png',
                                'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/af837359420d34418a11222bfb9215ea_1522443776478061795.png'
])
const item = ref<string[]>([ClickPagination.value[0], NoClickPagination.value[1], NoClickPagination.value[2], NoClickPagination.value[3]])

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

const P6HI = (index: number) => {
    item.value[index] = ClickPagination.value[index]
}
const P6HO = (index: number) => {
    if (!ClickFlag.value[index]) {
        item.value[index] = NoClickPagination.value[index]
    }

}
const ClickFlag = ref([false, false, false, false])
const paginationClick = (index: number) => {
    ClickFlag.value = [false, false, false, false]
    ClickFlag.value[index] = true
    swiperCopy.slideTo(index + 1, 10, false);
    paginationActive(index)
}

const paginationActive = (index: number) => {
    item.value[0] = NoClickPagination.value[0]
    item.value[1] = NoClickPagination.value[1]
    item.value[2] = NoClickPagination.value[2]
    item.value[3] = NoClickPagination.value[3]
    item.value[index] = ClickPagination.value[index]
}
</script>

<style scoped>
.swiper-slide .content{
    position: absolute;
    top: 78px;
    left: 188px;
    width: 930px;
    height: 480px;
    /* width: 797px;
        height: 413px; */
    overflow: hidden;
    /* z-index: 3; */
}
.line{
    position: absolute;
    top: 0px;
    left: 1036px;
    width: 20px;
    height:510px;
    align-content: center;
    z-index: 1;
    /* border: 2px solid red; */
}
/* .line img{
  
} */
.paginations {
    position: absolute;
    top: 72px;
    left: 1000px;
    /* width: 122px;
    height: 262px; */
    align-content: center;
    z-index: 2;
    /* border: 2px solid red; */
}

.paginations img {
    position: relative;
    width: 92px;
    height: 95px;
    /* margin-bottom: 3px; */
}
</style>