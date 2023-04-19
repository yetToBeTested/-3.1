<template>
    <div class="page7">
        <div class="wlimit">
            <img class="label" src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/b00ffd0818ffd932ed02ad73bceef636_4517631420097114764.png" alt="">
            <div class="middle">
                <page7swiper></page7swiper>
            </div>
            <div class="foot">
                <page7footicon @vxOpen="vxOpen"></page7footicon>
            </div>
            <!-- "微信号"展示页 -->
            <div class="vx" :style="{ display: displayVX, opacity: opacityVX }" @click="vxHide">
                <!-- :style="{ left: lvxDetal, top: tvxDetal, width: wvxDetal }" -->
                <div class="vxDetal" :style="{ left: lvxDetal, top: tvxDetal, width: wvxDetal }" @click.stop="">
                    <img class="vxHead"
                        src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/07/11/8d4e533df874da23cf6e7f451be57dca_944877516421628953.png"
                        alt="" draggable="false" />
                <!-- :style="{ left: lvxCode, top: tvxCode, width: wvxCode }" -->
                    <img class="vxCode" :style="{ left: lvxCode, top: tvxCode, width: wvxCode, height: wvxCode }"
                        src="https://webstatic.mihoyo.com/upload/puzzle/2021/11/19/6a8f260d01b18a97874a70611fac7f84_1193977791953494844.png"
                        alt="" draggable="false" />
                <!-- :style="{ fontSize: fsvxName }" -->
                    <div class="vxName">- 官方微信号 -</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import page7swiper from '../components/Page7Swiper.vue'
import page7footicon from '../components/Page7FootIcon.vue'
import { onMounted, onUnmounted, ref } from 'vue';
import { height } from 'dom7';

const emit = defineEmits(["canScroll"]); //当点击某个部件时发送给父组件以禁用swiper（不能滚动到下一页或上一页）
let canHideVX = ref(false); //是否可以点击底下"微信号"

//窗口的宽度和高度
let w2 = ref(0);
let h2 = ref(0);


//标准比例
const proportion = 250 / 108;


//底下"微信号"展示页的状态
let displayVX = ref("none");
let opacityVX = ref(0);
let lvxDetal = ref("");
let tvxDetal = ref("");
let wvxDetal = ref("");
let fsvxName = ref("");
let lvxCode = ref("");
let tvxCode = ref("");
let wvxCode = ref("");
const page7ZSY = () => {
    w2.value = document.documentElement.clientWidth;
    h2.value = document.documentElement.clientHeight;
    //微信公众号
    lvxDetal.value =
        (465 / 1250) * h2.value * proportion - (h2.value * proportion - w2.value) / 2 + "px";
    tvxDetal.value = (11 / 54) * h2.value + "px";
    wvxDetal.value = (325 / 1250) * h2.value * proportion + "px";
    //微信公众号 - text
    fsvxName.value = (14 / 540) * h2.value + "px";
    //微信公众号 - Code
    lvxCode.value = (155 / 465) * (325 / 1250) * h2.value * proportion + "px";
    tvxCode.value = 0.5 * (325 / 1250) * h2.value * proportion + "px";
    wvxCode.value = 0.33 * (325 / 1250) * h2.value * proportion + "px";

    // console.log("lvxDetal", lvxDetal.value, tvxDetal.value, wvxDetal.value, lvxCode.value, tvxCode.value, wvxCode.value);

}


//"微信号"展示页的显示和隐藏
const vxHide = () => {
    if (canHideVX.value) {
        opacityVX.value = 0;
        setTimeout(() => {
            displayVX.value = "none";
            emit("canScroll", true);
        }, 300);
    }
};

const vxOpen = (val: any) => {
    emit("canScroll", false);
    displayVX.value = "block";
    setTimeout(() => {
        opacityVX.value = 1;
    }, 10);
    setTimeout(() => {
        canHideVX.value = true;
    }, 300);
    console.log("收到:11111", val);
};

onMounted(() => {
    page7ZSY();
    window.addEventListener("resize", page7ZSY);
});

onUnmounted(() => {
    window.removeEventListener("resize", page7ZSY);
});

</script>

<style scoped>
.page7{
    width: 100%;
    height: 100%;
}
.page7 .wlimit{
    width: 100%;
    height: 100%;
    background: url("https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/e9c6adb1b8fb3bb72763a7f6ca265328_562346266611278910.jpg")center center no-repeat;
    background-size: cover;
}
.page7 .wlimit .label {
    position: absolute;
    width: 40px;
    height: 332px;
    left: 100px;
    top: 30px;
}

.page7 .wlimit .middle {
    position: absolute;
    top: 36%;
    /* right: 40px; */
    width: 1777px;
    height: 325px;
    transform: translate(-12%, -50%);
    /* overflow: hidden; */
}

.page7 .wlimit .foot {
    position: absolute;
    left: 0;
    /* top:524px; */
    bottom: 45px;
    width:100%;
   
    height: 85px;
    /* z-index: 1; */
}

.vx {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    transition: 0.3s;
}

.vxDetal {
    position: absolute;
    left: 465px;
    top: 110px;
    width: 325px;
}

.vxHead {
    width: 100%;
}

.vxCode {
    position: absolute;
    left: 110px;
    top: 160px;
    width: 107px;
}

.vxName {
    position: relative;
    top: -30px;
    left: 0;
    height: 14px;
    font-size: 14px;
    color: white;
    text-align: center;
}
</style>