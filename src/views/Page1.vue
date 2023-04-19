<template>
    <div class="page1">
        <div class="wlimit" :style="{ width: limitWidth }">
            <a  href="https://ys.mihoyo.com/main/" target="_blank">
                <img class="logo" src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/e4e920cc686af0183fcbfbeb64160b8e_2128577955602225015.png"
                alt="">
            </a>
            <div class="enterWeb">
                <a href="https://ys.mihoyo.com/main/" target="_blank">
                    <img 
                        @mouseover="enterWebHoverEnter"
                        @mouseleave="enterWebHoverleave"
                        :src= "enterBg"
                        alt="">
                </a>
            </div>
            <div class="ageTips">
                <img 
                @click="ageClickIn"
                src="https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/7257718ec90c92c4b5e9772f03b3579a_803742401669986540.png"
                alt="">
            </div>
            <div class="ageDetal" @click.stop="ageClickOut" :style="{ opacity: hideEffect, display: hide }">
                
                <img src="https://webstatic.mihoyo.com/upload/puzzle/2021/11/19/11e7a079077d5523f87ec34bf65a71fa_7483736760903107786.jpg"
                @click.stop="" class="ageDetal-bg" alt="" @dragstart.prevent />

                <img  src="https://webstatic.mihoyo.com/upload/puzzle/2021/11/19/cf76b2e566b7e1a132e470cd465b71c3_3970418835981795384.png"
                class="ageDetal-close" alt="" @dragstart.prevent />
            </div>
            <div class="player-bg">
                <img 
                    @click="videoClickIn"
                    @mouseover="playerHI"
                    @mouseleave="playerHO"
                    :src="playerBg"
                    alt="">
            </div>
            <!-- 视频展示页 -->
            <div class="videoDetal" 
            @click.stop="videoClickOut" 
            :style="{ opacity: videoHideEffect, display: videoHide }">
                <video 
                    v-if="videoShow" 
                    autoplay=true 
                    controls=true 
                    preload="auto" @click.stop="" class="videoDetal-bg"
                    src="https://webstatic.mihoyo.com/upload/static-resource/2022/09/16/f536b81cf99ea2c2a2ae87b1e643ec4c_7786134220728107534.mp4"
                >
                </video>
            </div>
            <div class="Download">
                <div>
                    <a href="">
                        <img 
                        class="PCDownload" 
                        @click="PCD"
                        @mouseover="PCDHI" 
                        @mouseleave="PCDHO" 
                        :src="pcdBg" 
                        alt="" 
                        @dragstart.prevent />
                    </a>
                </div>
                <div>
                    <a href="">
                        <img 
                        class="elseDownload" 
                        @click="elseD" 
                        @mouseover="elseDHI" 
                        @mouseleave="elseDHO" 
                        :src="elseBg" 
                        alt=""
                        @dragstart.prevent />
                    </a>
                </div>
                <div>
                    <a href="">
                        <img 
                        class="CloudDownload" 
                        @click="CDC" 
                        @mouseover="CDHI" 
                        @mouseleave="CDHO" 
                        :src="cdbg" alt=""
                        @dragstart.prevent />
                    </a>
                </div>
            </div>

        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const limitWidth = ref("100%");

const emit = defineEmits(["MWControl"]); //当点击某个部件时发送给父组件以禁用swiper（不能滚动到下一页或上一页）

let enterBg = ref("https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/17a21a1bfd999b4857d93e624f65fc06_286008124254636242.png")
const enterWebHoverEnter = () =>{
    enterBg.value = "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/73e2e23f71c7191c7c469b0615f0722f_8184213760734682046.png"
}
const enterWebHoverleave = () =>{
    enterBg.value = "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/17a21a1bfd999b4857d93e624f65fc06_286008124254636242.png"
}

let hideEffect = ref(0);
let hide = ref("none");

let mw = ref(true);

const ageClickIn = () => {
    hide.value = "block";
    mw.value = false;
    emit("MWControl", mw.value);
    setTimeout(() => {
        hideEffect.value = 1;
    }, 10);
}
const ageClickOut = () => {
    hideEffect.value = 0;
    setTimeout(() => {
        hide.value = "none";
        mw.value = true;
        emit("MWControl", mw.value);
    }, 300);
};

let playerBg = ref("https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/82b17077c97738cfcfe04c4cd8f9fdd2_7956113854378281984.png")
const playerHI = () => {
    playerBg.value = "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/cd7d2754eefcdc2838462a7792b1d722_6876927132869721502.png"
}
const playerHO = () => {
    playerBg.value = "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/82b17077c97738cfcfe04c4cd8f9fdd2_7956113854378281984.png"
}

let videoShow = ref(false);
let videoHide = ref("none");

let videoHideEffect = ref(0);

const videoClickIn = ()=>{
    videoShow.value = true;
    videoHide.value = "block";
    mw.value = false;
    emit("MWControl", mw.value);
    setTimeout(() => {
        videoHideEffect.value = 1;
    }, 10);
}

const videoClickOut = () => {
    videoHideEffect.value = 0;
    setTimeout(() => {
        videoHide.value = "none";
        videoShow.value = false;
        mw.value = true;
        emit("MWControl", mw.value);
    }, 300);
};

let pcdBg = ref("https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/ae2fdfb14f0fc99b56d2b213b2991f83_2759501618393525706.png")
const PCD = () => {
    alert("暂无下载\n官网是一点就会下载:>_<:");
};
const PCDHI = () => {
    pcdBg.value = "data:image/webp;base64,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"

}
const PCDHO = () => {
    pcdBg.value = "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/ae2fdfb14f0fc99b56d2b213b2991f83_2759501618393525706.png"

}

let elseBg = ref("https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/ec1f7a5056ccabef111c4e515c95a5c5_3002707723343361549.png")
const elseD = () => {
    alert("暂无下载\n官网是一点就会下载:>_<:");
}
const elseDHI = () => {
    elseBg.value = "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/c01a1683b6401c49bfb294bdf685dbd3_8579524595952653907.png"
}
const elseDHO = () => {
    elseBg.value = "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/ec1f7a5056ccabef111c4e515c95a5c5_3002707723343361549.png"
}

let cdbg = ref("https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/48a789132b0896dcfcdabc72961ad7dc_9101560904698408188.png")
const CDC = () => {
    alert("暂无下载\n官网是一点就会下载:>_<:");
}
const CDHI = () => {
    cdbg.value = "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/fe36858d889cc0dad020e1b03c748d2d_4086126073770837005.png"
}
const CDHO = () => {
    cdbg.value = "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/48a789132b0896dcfcdabc72961ad7dc_9101560904698408188.png"
}
</script>



<style scoped>
.page1 {
    position: relative;
    width: 100%;
    height: 100%;
}
.page1 .wlimit {
    height: 100%;
    background: url("https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/fc1e1f63445f98fe943435474d2bc59f_7853406441613588886.jpg") center center no-repeat;
    background-size: cover;
}
.page1 .wlimit .logo{
    position: absolute;
    width: 148px;
    height: 114px;
    left: 76px;
    top: 2px;
    object-fit: contain;
}
.page1 .wlimit .enterWeb {
    position: absolute;
    width: 119px;
    height: 32px;
    left: 1136px;
    top: 30px;
    object-fit: contain;
}
.page1 .wlimit .ageTips{
    position: absolute;
    width: 65px;
    height: 84px;
    left: 105px;
    top: 545px;
    object-fit: contain;
}

.page1 .wlimit .ageDetal {
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    align-content: center;
    vertical-align: center;
    transition: all 0.3s;
    z-index: 10;
}



.page1 .wlimit .ageDetal-bg {
    position: relative;
    width: 520px;
    height: 390px;
    top: 135px;
    left: 420px;
    object-fit: contain;
}

.page1 .wlimit .ageDetal-close
{
    position: absolute;
    width: 34px;
    height: 34px;
    top: 135px;
    left: 939px;
}
.page1 .wlimit .player-bg {
    position: absolute;
    width: 52px;
    height: 52px;
    left: 870px;
    bottom: 94px;
    /* object-fit: contain; */
}

.page1 .wlimit .videoDetal {
    position: relative;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    align-content: center;
    vertical-align: center;
    transition: all 0.3s;
    z-index: 10;
}

.page1 .wlimit .videoDetal .videoDetal-bg {
    position: absolute;
    width: 456px;
    height: 256px;
    top: 200px;
    left: 450px;
    object-fit: contain;
}
.page1 .wlimit .Download{
    position: absolute;
    width: 660px;
    height: 39px;
    left: 380px;
    bottom: 32px;
    display: flex;
    margin-bottom: 5px;
}
.page1 .wlimit .Download div{
    width: 215px;
    height: 39px;
    margin-right: 5px;
}
</style>