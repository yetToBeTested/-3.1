<template>
    <swiper 
    @swiper="onSwiper7" 
    :direction='"horizontal"'
    :speed="300"
    :loop="true"
    :loopAdditionalSlides="4"
    :slidesPerView="'auto'"
    :centeredSlides="true"
    :observer="true"
    :observeParents="true"
    :nested="true"
    :resistanceRatio=0
    :watchSlidesProgress="true"
    :autoplay="{
        delay: 7000,
        disableOnInteraction: false, 
        pauseOnMouseEnter: false, 
    }"
    :navigation="{
        prevEl: '.swiper-button-prev',
        nextEl: '.swiper-button-next',
    }" 
    :pagination= "pagination"
    :modules="modules" class="mySwiper7">

        <swiper-slide class="swiper-slide7">
            <div class="mask"></div>
            <img class="content" src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/36627963e3a3587ba14bc095ac433c74_4985115587357161481.png" alt=""> 
        </swiper-slide>

        <swiper-slide class="swiper-slide7"> 
            <div class="mask"></div>
            <img class="content" src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/4275856d730de7c4ffcac5f75a09217d_4508965882865448082.png" alt="">
        </swiper-slide>

        <swiper-slide class="swiper-slide7"> 
            <div class="mask"></div>
            <img class="content"
                src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/671bb993fa5b484c6c558f9beb7c1576_6672175538055131782.png"
                alt="">

        </swiper-slide>

        <swiper-slide class="swiper-slide7">
            <div class="mask"></div>
            <img class="content"
                src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/e110ad1aa81fb20f35eeaae2f943f6af_6402335598165177262.png"
                alt="">

        </swiper-slide>

        <swiper-slide class="swiper-slide7">
            <div class="mask"></div>
            <img class="content"
                src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/bfcbe6709cdd8026474261b52df3436a_6609913684335206613.png"
                alt="">

        </swiper-slide>

        <!-- <swiper-slide>
            <div class="mask"></div>
            <img class="content"
                src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/36627963e3a3587ba14bc095ac433c74_4985115587357161481.png"
                alt="">

        </swiper-slide> -->

    </swiper>

    <div class="swiper-pagination7">

    </div>

    <div class="paginations">
        <img :style="{
            width: '23px',
            height: '23px',
            margin: '0 30px 0 0',
        }" v-for="(item, index) in paginationsP7NoClick" @click="paginationClick(index)" :src="item" alt=""
        class="paginations_image"    draggable="false" />
    </div>
    <!-- 前进后退按钮 -->
    <div class="swiper-button-prev">
        <img class="leftArrowBg" draggable="false" :src="leftArrowChangeBg" alt="" />
    </div>
    <div class="swiper-button-next">
        <img class="rightArrowBg" draggable="false" :src="rightArrowChangeBg" alt="">
    </div>
</template>

<script setup lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";
// import "swiper/css/effect-fade";
// import "swiper/css/navigation";
// import "swiper/css/pagination";

// import required modules
import { EffectFade, Navigation, Autoplay, Pagination } from "swiper";
import { onUnmounted, onMounted, onUpdated, ref, watch } from "vue";
const modules = [EffectFade, Navigation, Autoplay, Pagination]

let canChange = ref(true);
let prevId = ref(0);

const leftArrowChangeBg = ref(
    "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/af16bf700335b86b0cd1c8989d2fc69d_6688319589631573492.png"
);
const rightArrowChangeBg = ref(
    "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/04e39934228d4f5c7296999703025fe7_6875357041806353672.png"
);




const paginationsP7NoClick = ref([
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/32620ecf5707db4c7a9ea4875303ccb0_9192751032228843208.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/32620ecf5707db4c7a9ea4875303ccb0_9192751032228843208.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/32620ecf5707db4c7a9ea4875303ccb0_9192751032228843208.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/32620ecf5707db4c7a9ea4875303ccb0_9192751032228843208.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/32620ecf5707db4c7a9ea4875303ccb0_9192751032228843208.png'
    ]
)

const temp = ref<string[]>([
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/32620ecf5707db4c7a9ea4875303ccb0_9192751032228843208.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/32620ecf5707db4c7a9ea4875303ccb0_9192751032228843208.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/32620ecf5707db4c7a9ea4875303ccb0_9192751032228843208.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/32620ecf5707db4c7a9ea4875303ccb0_9192751032228843208.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/32620ecf5707db4c7a9ea4875303ccb0_9192751032228843208.png'
])

const paginationsP7Click = ref('https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/f0162c51312a81254e7bbbe6e95c9a28_296308618283061002.png')

const itemRefs = ref<any>([]);

const pagination = ref<any>({
    el: '.swiper-pagination7',
    // clickable: true,
    type: 'custom',
    renderCustom: function (swiper: any, current: number, total: number) {
        var paginationHtml = "";
        for (var i = 0; i < total; i++) {
            // 判断是不是激活焦点，是的话添加active类，不是就只添加基本样式类
            if (i === (current - 1)) {
                // console.log("total:", current, total);
                paginationActive(i)
                // itemRefs.value.src = paginationsP7Click.value

            }

        }
        return paginationHtml;
    }
},)

var page7Swiper: any = ref()
const onSwiper7 = ((swiper: any) => {
    page7Swiper = swiper
})


// const temp = p4Paginations.value
const paginationClick = (index: number) => {
    // console.log(index);
    page7Swiper.slideTo(index +5 , 100, false);
    paginationActive(index)
}

const paginationActive = (index: number) => {
    for (let i = 0; i < paginationsP7NoClick.value.length; i++) {
        paginationsP7NoClick.value[i] = temp.value[i]
    }
    paginationsP7NoClick.value[index] = paginationsP7Click.value
    // document.getElementsByClassName("paginations_image")
    // console.log("document.getElementsByClassName", document.getElementsByClassName("paginations_image"));


}
//swiper切换效果(卡片轮播),放到swiper切换进度调用
const swiperProgress = (swiper: any, progress: any) => {
    for (let i = 0; i < swiper.slides.length; i++) {
        var slide = swiper.slides.eq(i);
        // var slideProgress = Math.round(swiper.slides[i].progress) ;
        var slideProgress = swiper.slides[i].progress;

        // console.log("progress:", progress, "slideProgress", i, slideProgress);
        // console.log("hideDistance.value:", hideDistance.value, "distance.value:", distance.value);
        let modify = 1; //移动倍数
        if (Math.abs(slideProgress) > 1.5) {
            modify = (Math.abs(slideProgress) - 1) * 0.3 + 1;
        }
        if (modify >= 1.6) modify = 1.6;
        let translate = "";
        if (Math.abs(slideProgress) > 1.5) {
            // translate =
            //     (Math.abs(slideProgress) / slideProgress) *
            //     ((Math.abs(slideProgress) - 1) * hideDistance.value + 1 * distance.value) +
            //     "px";
            // translate =
            //     (Math.abs(slideProgress) / slideProgress) *
            //     ((Math.abs(slideProgress) - 1) *608 + 1 * 474) +
            //     "px";
            translate =
                (Math.abs(slideProgress) / slideProgress) *
                ((Math.abs(slideProgress) - 1) * 608 + 1 * 474) +
                "px";

        } else {
            // translate = slideProgress * modify * distance.value + "px";
            translate = slideProgress * modify * 400 + "px";
        }
        let scale = 1 - Math.abs(slideProgress) / 5;
        let zIndex = 99 - Math.abs(Math.round(10 * slideProgress));
        // console.log("translate", i, translate, scale, zIndex);
        slide.transform("translateX(" + translate + ") scale(" + scale + ")");
        slide.css("zIndex", zIndex);
        slide.css("opacity", 1);
        if (Math.abs(slideProgress) > 1.5) {
            slide.css("opacity", 0);
        }
    }
};

//改变蒙版层
const maskOpacityChange = (swiper: any) => {
    for (let i = 0; i < swiper.slides.length; i++) {
        swiper.slides[i].firstChild.style.opacity = 1;
    }
    // console.log("swiper.activeIndex:", swiper.activeIndex);
    if (swiper.activeIndex < 10) {
        swiper.slides[swiper.activeIndex].firstChild.style.opacity = 0;
        // console.log("swiper.activeIndex:", swiper.activeIndex);
        // console.log(swiper.activeIndex);
        swiper.slides[swiper.activeIndex + 5].firstChild.style.opacity = 0;
    }
    if (swiper.activeIndex >= 10) {
        // console.log("swiper.activeIndex:", swiper.activeIndex);
        swiper.slides[swiper.activeIndex].firstChild.style.opacity = 0;
        swiper.slides[swiper.activeIndex - 5].firstChild.style.opacity = 0;
    }
};

const slideZSY = () => {
    for (let i = 0; i < page7Swiper.slides.length; i++) {
        page7Swiper.slides[i].style.width = "562px";
        // console.log('page7SwiperEvent.value.slides[i].style.width', i, page7Swiper.slides[i].style.width);
    }
}

onMounted(() => {
    page7Swiper.on("progress", (swiper: any, progress: any) => {
        // console.log(progress);
        swiperProgress(swiper, progress);
    });
    //swiper切换的动作
    page7Swiper.on("setTransition", (swiper: { slides: string | any[]; }, transition: number) => {
        for (var i = 0; i < swiper.slides.length; i++) {
            swiper.slides[i].style.transition =
                "all" + " " + transition / 1000 + "s" + " " + "ease";
        }
    });

    //slide切换时
    page7Swiper.on("slideChange", (swiper: any) => {
        setTimeout(() => {
            maskOpacityChange(swiper);
        }, 10);
    });

    // // swiper开始切换时
    // page7Swiper.on("transitionStart", (swiper: any) => {
    //     canChange.value = false;
    //     setTimeout(() => {
    //         // prevId.value = page7SwiperEvent.value.activeIndex % 5;
    //         // paginationActiveChange(page7SwiperEvent.value.realIndex);
    //     }, 10);
    // });

    // // swiper结束切换时
    // page7Swiper.on("transitionEnd", (swiper: any) => {
    //     canChange.value = true;
    // });

    // //每一个slide都有一层较暗的蒙版层,slide切换时改变对应的蒙版层
    maskOpacityChange(page7Swiper);
    slideZSY();
    window.addEventListener("resize", slideZSY);

    // console.log("itemRefs.value", itemRefs.value.src);
    // itemRefs.value.src = paginationsP7Click
})

onUnmounted(() => {
    window.removeEventListener("resize", slideZSY);
});



</script>

<style scoped>
.mySwiper7 {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    /* background-color: rgba(255, 0, 0, 0.2); */
    overflow: visible;   
}

.swiper-slide7 {
    height: 100%;
    position: relative;
    top:-0px;
    left: -0px;
}

.mask {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    transition: 0.3s ease;
    opacity: 1;
}

.swiper-slide .content {
    width: 100%;
}

.paginations {
    position: relative;
    top: 350px;
    left: 780px;
    width: 240px;
    display: flex;
    align-content: center;
    z-index: 1;
    /* border: 2px solid red; */
}

.swiper-button-prev {
    position: absolute;
    left: 530px;
    top: 130px;
    width: 63px;
    height: 62px;
    outline: none;
    z-index: 1;
}

.swiper-button-next {
    position: absolute;
    left: 1185px;
    top: 130px;
    width: 63px;
    height: 62px;
    z-index: 1;
}
</style>