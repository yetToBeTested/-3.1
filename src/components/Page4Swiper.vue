<template>

    <swiper
    @swiper="onSwiper" 
    :spaceBetween="30" 
    :effect="'fade'" 
    :loop=true
    :navigation="{
        prevEl: '.swiper-button-prev',
        nextEl: '.swiper-button-next',
    }" 
    
    :autoplay="{
        delay: 2500,
        disableOnInteraction: false,
        pauseOnMouseEnter: false, 
    }"
    :fadeEffect= "{
        crossFade: true,
    }"
    
    :pagination= "pagination"
    
    :modules="modules" class="mySwiper">
        
        <swiper-slide>
            <div class="bg" style="background: url('https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/22/e4338637697dd1c42b34e61bef7331d5_18783792095703369.png') center center / cover no-repeat; overflow: hidden;">
               
                <img class="content" @click="video4ClickIn(0)" @mouseover="player4HI" @mouseleave="player4HO" 
                :src="player4Bg" alt="" />
                
                <!-- 视频展示页 -->
                <div class="videoDetal4" @click.stop="videoClickOut(0)" v-if="videoShow[0]"
                :style="{ opacity: videoHideEffect[0], display: videoHide[0] }">
                    <video  autoplay=true controls=true 
                    preload="auto" @click.stop="" class="videoDetal-bg4"
                        src='https://webstatic.mihoyo.com/upload/static-resource/2022/09/27/651cceb972595d569792b147411c5d38_2641715154897002451.mp4'>
                    </video>
                </div>
                
                <img class="audiostylec" :src="audio[0].chinese" 
                alt="">

                <img class="audiostylee" :src="audio[0].english" 
                alt="">
            
            </div>
        </swiper-slide>

        <swiper-slide>
            <div class="bg" style="background: url('https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/70eb3e611644c94fcf85ccc139c316b4_8538278292339975655.png') center center / cover no-repeat; overflow: hidden;" >
                <img class="content"
                    @click="video4ClickIn(1)"
                    @mouseover="player4HI"
                    @mouseleave="player4HO"
                    :src="player4Bg"
                    alt="" />

                <!-- 视频展示页 -->
                <div class="videoDetal4" @click.stop="videoClickOut(1)" v-if="videoShow[1]"
                :style="{ opacity: videoHideEffect[1], display: videoHide[1]}">
                    <video  autoplay=true controls=true preload="auto" 
                        @click.stop="" class="videoDetal-bg4"
                        src='https://uploadstatic.mihoyo.com/hk4e/upload/officialsites/202009/%E6%B8%A9%E8%BF%AA%E6%BC%94%E7%A4%BA_1601094353_1057.mp4'>
                    </video>
                </div>
                
                <img class="audiostylec" :src="audio[1].chinese" alt="">
                <img class="audiostylee" :src="audio[1].english" alt="">
                
            </div>
            
        </swiper-slide>

        <swiper-slide>
            <div class="bg"  style="background: url('https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/4f38f8dcf9a9edb020e920fcdc34c4c3_2879764323151677973.png') center center / cover no-repeat; overflow: hidden;">
                <img class="content"
                    @click="video4ClickIn(2)"
                    @mouseover="player4HI"
                    @mouseleave="player4HO"
                    :src="player4Bg"
                alt="" />

                <!-- 视频展示页 -->
                <div class="videoDetal4" @click.stop="videoClickOut(2)" 
                :style="{ opacity: videoHideEffect[2], display: videoHide[2]}" v-if="videoShow[2]">
                    <video  autoplay=true controls=true preload="auto" 
                    @click.stop="" class="videoDetal-bg4"
                    src='https://webstatic.mihoyo.com/upload/static-resource/2022/09/26/6c91e518c7e3c8bb4186f5d8ffa7870b_4866638007303870176.mp4'>
                    </video>
                </div>
                
                
                <img class="audiostylec" :src="audio[2].chinese" alt="">
                <img class="audiostylee" :src="audio[2].english" alt="">

              

            </div>
        </swiper-slide>

        <swiper-slide>
            <div class="bg" style="background: url('https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/2de22b84e4272ce0b7f34faa7bb60876_5673119290051923035.png') center center / cover no-repeat; overflow: hidden;">
                <img class="content"
                    @click="video4ClickIn(3)"
                    @mouseover="player4HI"
                    @mouseleave="player4HO"
                    :src="player4Bg"
                    alt="" />

                <!-- 视频展示页 -->
                <div class="videoDetal4" 
                @click.stop="videoClickOut(3)" 
                :style="{ opacity: videoHideEffect[3], display: videoHide[3]}"
                    v-if="videoShow[3]">
                    <video autoplay=true controls=true preload="auto" @click.stop="" class="videoDetal-bg4"
                        src='https://webstatic.mihoyo.com/upload/static-resource/2022/10/12/91b92a3f654d409189eae5ee8e74e41c_4117568113820660411.mp4'>
                    </video>
                </div>
                
                <img class="audiostylec" :src="audio[3].chinese" alt="">
                <img class="audiostylee" :src="audio[3].english" alt="">
                    
            </div>
        </swiper-slide>

        <swiper-slide>
            <div class="bg" style="background: url('https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/7143d3f351d84877a2b9f1f070e2acf2_6055344110966614834.png') center center / cover no-repeat; overflow: hidden;">
                <img class="content"
                 @click="video4ClickIn(4)"
                 @mouseover="player4HI"
                 @mouseleave="player4HO"
                :src="player4Bg"
                alt="" />
                
                <!-- 视频展示页 -->
                <div class="videoDetal4" 
                    :style="{ opacity: videoHideEffect[4], display: videoHide[4]}"
                     @click.stop="videoClickOut(4)" 
                    v-if="videoShow[4]">
                        <video autoplay=true controls=true preload="auto" @click.stop="" class="videoDetal-bg4"
                            src='https://uploadstatic.mihoyo.com/hk4e/upload/officialsites/202012/%E9%98%BF%E8%B4%9D%E5%A4%9Agame_1608605635_5249.mp4'>
                        </video>
                </div>
                
                
                <img class="audiostylec" :src="audio[4].chinese" alt="">
                <img class="audiostylee" :src="audio[4].english" alt="">

            </div>
        </swiper-slide>
    
    </swiper>
   
    <div class="swiper-pagination4" >
       
    </div>

    <div class="paginations" id="p4pag">
        <img :style="{
            width: '40px',
            height: '40px',
            margin: '0 40px 0 0',
        }" 
        v-for="(item, index) in p4Paginations"  
        @click="paginationClick(index)" 
        :src="item"  alt=""
        draggable="false" />
    </div>

    <!-- 前进后退按钮 -->
    <!-- :src="leftArrowChangeBg" -->
    <div class="swiper-button-prev" id="prev">
        <img class="leftArrowBg4" draggable="false" :src="leftArrowChangeBg4" alt="" />
        
    </div>
    <div class="swiper-button-next" id="next">
        <img class="rightArrowBg4" draggable="false" :src="rightArrowChangeBg4" alt="">
    </div>

</template>

<script setup lang="ts">
import { Swiper, SwiperSlide} from "swiper/vue";

// Import Swiper styles
import "swiper/css";
import "swiper/css/effect-fade";
// import "swiper/css/navigation";
// import "swiper/css/pagination";

// import required modules
import { EffectFade, Navigation, Autoplay, Pagination} from "swiper";
import { onMounted, onUpdated, ref, watch } from "vue";
const modules = [EffectFade, Navigation, Autoplay, Pagination]

const player = ref("https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/736d7f6fd4149b3d2f0b2e4a9f06089c_2087247614896253109.png")
const playerClick = ref('data:image/webp;base64,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')

const player4Bg = ref()
player4Bg.value = player.value

const leftArrowChangeBg4 = ref(
    "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/99f21ec58d52e7ebf0ec9d9f022d9d14_1589204872202004144.png"
);
const rightArrowChangeBg4 = ref(
    "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/f688748fd532d201b9f8810e275b0e3f_6877776947729540757.png"
);
const p4Paginations = ref<string[]>([
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/49b0d4edaff8696180b04b2cb18eca76_8159614929720420543.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/7d35c07fac5ed145b3429164f1bc51fa_888370857059316630.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/cca3e4d75acc7d5974aa60f51e2fd6b9_8165144317195169263.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/3644b28e3f4cb2e9af541a31ec4619df_1924560429513453825.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/31d2ae72de15c1b558f4c7d9319a0974_783869415668509656.png'
])

const temp = ref < string[] >([
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/49b0d4edaff8696180b04b2cb18eca76_8159614929720420543.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/7d35c07fac5ed145b3429164f1bc51fa_888370857059316630.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/cca3e4d75acc7d5974aa60f51e2fd6b9_8165144317195169263.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/3644b28e3f4cb2e9af541a31ec4619df_1924560429513453825.png',
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/31d2ae72de15c1b558f4c7d9319a0974_783869415668509656.png'
])

const p4PaginationsSel = ref<string[]>([
    'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/d636a0b0981878d7f16d763cff67948d_8379394089171599598.png',
    'data:image/webp;base64,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',
    'data:image/webp;base64,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',
    'data:image/webp;base64,UklGRrQZAABXRUJQVlA4WAoAAAAQAAAAVAAAVAAAQUxQSOoGAAABh8agbSRH71zhz/k7g4jIwz3veckZ8hryMBGLPAbTh+EcfpTlzH0zc90IAShs27a0zfd1I7XFmjVJV0pdktXTTurubt8331KfSzt396TzrSVzd3f3pZPwm7Y3aQJE9N+B2zaONLpt027qbuInwE9YQ+K01gWD+4Xrdx49eXTnurB/cEHrtEQDC/lgjeaahQevDA/ObSnLzU61pGbnlrXMHXRcObiwxmyUKUId17Dpor2v0hJlVAfRHo2hg9TGKEtln/3SpoY4NSRHm2I7c3zBFF7HwBcYHZ+z4PiILUULSVGlLhS2VUer/RvA6JrtwsJUlYRzGLvg3MY8E+OlHSq9ieOjY6J5zqRXeZlDxpS/8ZwtloU06Ovsu8uNlEeajsvoWL7v3O3nL169eH773L7lHRmczqMDlLF8j71ODwlgElY553BkDloX17L11uvPX8fcIol77Ovn17e2tcTpaLKV3GxhVSIDfwkutO/KDiHzh5dve/rph+gLPz493VYeTmYPse48XBgM/9DMELo4iuh7RIfwziX6zo+3QkcEQxTibMIMDfzB0DPSRK6j0Nqzn36L/vH709naUHKNNo/2hsF3IlYcLQwAgMC0HW+IO39v3uxICwSAgJLTKyPgK5HrHFaGiP3vgUuUBteD/4lIdurRNRx8I3xoOJMGQMWsf+8WpcL9fn0MBYDOcqw0wBdClxyz/jvozJHvopR8HyFGgLYOd/tSWfAsZx4NgMm9/kuUll/XcxkATN6ZGeP/KV1+sYUFwJTd/S1Kze+7ZQwAtuVCOT3OQSWfXKIBQBfd+yNKz597RTQAzZKTyZT3MHHNXh4AlX2TOKT/3cymAPB710z0ejBNZ60UgFinR6r0ic5YAJT1bBPjLSScmBMMQL/+uygX39frAQTPOZHg5VD17osEEDjjnSgf72YEAojc16vyOKj08+U0QGU8covy4X6UQQF0xfl0igy6pZsMAML2jIlyMrYnDIBh0zIdeU27kE8BTD0RJ2dUAwNQ+RfSiIu6Z4cJwKTRP6K8/BEmATDt6FH/C/Gjdcy/ij+KcvPxX81M3Wg8ALZpJBaA6eRvUW5+nzIBiB1pYgHD5gENQFW8FeXnbQUFaAY2GQDLpWkUoN3uEuXHtV0LUNMuWxBY7+ABJDxzi/LjfpYAgB9uCDQu79cCAe2fRSXwuT0A0PYvNyYfqWIA3d9nJeDaoQOYqqPJuVcnA4i85RaVgPtWJIDJV3M7h3kAWa9FZfA6CwBv7+wfMgDs3xRl8LmdBQyDA5vmqYEJi76IyuDLogmAet6mQy1BQOgul6gMXLtCgaDWQ0IZDZicf0Rl8MdpAqhS4XoeAO6WqBRucwByrt3NBsA/F5XCcx5A6u2HqQCiX4hK4UU0AMuDx2YAMa9EpfAqBoD5sUJPCo1WaDFnGQWEn1PM/jgfTuyPQ61BgH7fmKgMfu7XEzuZeOeoVnwTlcHXFSrinTMwZAACOhXzduwIIN6OHQ5FvscV9sW54/HFST5KfBt3KOTbuNPj26jIr/gKY2CDIu0NWC4rzjK6ZFGsDedpbZ5WgLV52pu1ifjRGsIu/iC/XdzMetjFXi14QXYL3ulpwXv3NRpk9zUaCV/jIulrQLdMGV7RXtIrWq7z4r9V0gCVKbP/lkkBdNWFdIoMUPUfilKIpxl1qN+bPphwal4IAP0GGX3iDXoAIfNPefOJwTRfUIb3nn2+mfGuM6zdrQidYffqieMqIotJReS+LIrI/WJCEVnkSMQ40GXnmwntpuLvT/qjgtBums4W0hiP4Jmncok2Fd+QXGW6WUSMQu4pH1QmQNM1TOhhjHVUYj1MsDIeepgWvmBY6SCVu1iJlbtYilDm7D4qdwC3xu6hMc54KJnG+HBmKIhRta/h/FFDC0g1NH2nRGroznRSDS04sjzCP922kdzf+jpJdNs6Pfl2aRzpCYM/aGYINo4iRjKiU3jn8qeed0JnBDFHVIRNmKmFfwQX2ndYySUZEF6+49knl28xn55tLw8PIBtq3WEvDIa/MImrhFkc+eqgdXFtO+68/vx1zHMVuse+fn59Z0dbnI4mW8nNEgaTGEiAvs6xp9zo8TpmQyMzO1fsO3v7+ctXL5/fPrtvRWdmZChLNooylu9xEFVIARvbdX5jnonx0g6V3sTx0THRPGfSqzzSAMaUt/F8VywLyVClLhS21cZo/FtKMbXbhIVpKkiKNsU2embhNF7n2zwxOn7awjOjthQtJEcd17jlsr2v0sIb1EEUPGYvSG3gLZV9hy9vaYxTQxZYo7lm4cErjsG5LaU5qWazOTWntGXuoOPKoYW1ZiML+WANidPbbEMHnNduPXz88NY154EhW9v0RIO/MQBWUDggpBIAAPBAAJ0BKlUAVQA+LQ6GQqGGx625BgCxLYAQZkfv6rzNqW/X/6v+iOKtLR228tfwM9RX6c9gD9U+kP+4fqA/Zb9o/dq/1X7Qe4//Bf5j2AP6X/pPWg/63sHf3z/kewB+zPpk/ul8EH9i/4P7k/Ah+y//69gD0AOAA7WP7j+JPmj+JfI/1P+ofsr/Zv/N7rf5f3cubf9P+QHuF/HfrR9m/pn7Mf2P/uf8L4m/zHgn8Gf5v1AvxL+R/2r+q/st/Zv/H/1Pa/2R1bvQC9Tfl3+E/uH7g/4P0Uv5H8gPcj6v/7j8jvoB/jn9D/uv5b/3z///Pf98/xHjF/UP7X/lfu3+wL+O/zX/Zf3r9xf8/9KH8F/uf8J+2/+U9rP5x/W/9l/c/3D/xv///AT+Pfy7/A/2L/I/8r+8f/z/n/dl6+v2E9i39Pvn/Z1AfohqSGSXPnygadExGNjDtlZDrUHialfc31Au/fw1AzB60ugJssHmb+5IO/xxzeHXeyVabBhHv/ocvWkXKikcES/eLhdbZ+2axgSwaCkffFGQbI+dEHCTiNB2tyVfCBzKr5M5njK/fzEIS9vUY7tOVBWy1HL4LXip37vrEQF8xjuFB8eq5u5ALareUSvnZ6tTnImx2DCyx3eUB9TUN8ggodqhQnMM9AutvPtVhkcgsAFTNtG1J0XmCl1Js0SYcb7P6/7rswH7mgLhAAD+/+r7hI/LoNrUACKDJ1GUuRwLYy9eQMT72I+LjhnJM1xNRkDvuc1+JHJBw/Yup11hCFygyXMojhRIEXC/SHB2LlZfPh0wZW0tOuETfmLR2wG7SYDvOVO8/PUisOsBDZgSJa0HGWEfqJKKUMZCIIq49zr4eBB0PlDXC4ydvreX6Fvtibc+jjELI4e0eVFnmDZhop5oe6DgJKJi2/lat6+GO1heLRAV0fMrDam8MJsw8kDUH0J/yBaOfxKjE/fmT+zp3ZVJRP8ES7EUViY/qI1f0ogL62B8VSJ9Wh6miisvbz5dtnaAgueyXCm8tDPqylT5smVCmxBfg7hA5SHIS/44mkLgJGxBS8B5+cAi4CXCvCvsFaz1VMS8L2fqZ0ABZzKvSSz3IkTczsY+XSUrms9mm0kfAkTt+xzEVkjbbEIoVqPwFKd4K6BEkwKO3wpIxI2CH/d3wRzXCcJ3EFgBI7gCC6OtlULmPEkSe3+7gGhgYCJNT3iIlwSSsgzjogUho/5cjy7Gc3p3fZbvjPqDHDAisj/waFQ01AEgMQiXSRWC0s1tX+AaMTr7OlVabFLLHgvQ+L0mNVzfMuQiQDj3fGt/g09jD/lqoj9jGwufVR3hrgSluvOn9H6xFYPq0/Scz0QkoyufRw7RNeh51/QyaGA3sXb+L3qxoWNgNf3FNujgI8l9jvZ0zTAMBSaXwLbiM+ipVXNvxQphxA/fVolon52oe1RnneZ+0lIkeP9Oe4Bqc1yrnrPefE47GROS17dRrDeyZSjL8j5YMLEPjS6xC03mmvdngZqZ3XTC8lilktjSa7u17OTgHyHmRHPxo4Qz8GaFHpTxha4txw9I7XldYoCoNGoVdSLQFpitiRYcjjfi926cXrMoVDI1gm4oiTcZgeEG6fnEzhfTeJJ2xKlL5fvTPH5HSgQiHnvbl5zvmGqVd02e2cgoHHTo3CsxkYpf4csTlJacE2gglqpot0xohj8/MPU1knZeE81G7tAwxFGHlwXpujGXJzDrhH4rtAho4FAmY+bdu4ygidvZf5pT3ojY3EeTy/B8KI8VqXoOMxfUIFxbCsUasYEsqpf63UmAP0C2V67gvKiO3IKlJZ8PWuVAvDetGQVH7EP1vG4xjkUxSs3DJoS4Tqd2NnGTmEJn7+rTSJh6HtmNMuJYsRiI/CDru8W5+mJomcXhloN6nw5ap4V2/jLdMg0Qlrbf6KItJEfM4Goe2bmecrzJZv3l0MC5aKsvrFXxRXm7QnuNUy+DbYanpPsKyX4H5cu8OIaGa2ATXkrJJSjhU7WBQpotD8i5tmlmPJDNjX6g0B87tqRU5nL13p8QDc2yVswKJ87eRSGxJNFV6aHATpk2pavNqTKVLAonK/fzRxpN3JLxDofwJu1582NS5Hf6GG9Oj/2UmM893Zh/dfGeqWxAL+IkDu1SbzOIohLDhl5alkLbCAnjERPP5AHFFHlPpMOYXnpwHhTB5itdq3/pS8iefCtk3N5ollfmz65xrUVlAyTgkqURFVMD6NzywngMLtJY2fShtxCcIiV4EYqSSJrIb0pADRwCwyJRHwU6lrSoYjjR6HbOLSEDUc3sITUITi6zYclvXyyFN8hUYIbXTMr+RBYzDk/MjjJ3wvj/sGZienrYlw0n0cYVe4CxzdUBba6QEJiuiFkYs61FvbisEbfEeKveN+QgKL2ya+cWheB7TJx6chSmUuZwtBtkRqHC3CM4Z5aJCDEx/wvx+9O5uT3i1dJpuRw5bvSRQbxYC+sY+QdCH0CfZh7AG2rKa3SFj+svk9K8KkgDjFVDxWij2d+crhhOfoaliJ9e7tvgfI4kCZr/d5+LVc9XBpa9mD/L0T67Bi/I+scrmBJmRDa7CCVjm5moatePKCrbOP+eZjYB2C1eFY4QZY1Zn/gZSiQErlbNQCtRoabLCV0nBnSxPhqgstaTPVyG6LwAfrIRiAiAmwqSI2WTIQiuForvcblS2rlQu9pzqhlOqldZvlSPSOz5DBD4szxky97rCnfRuKMjq4P6LR0K2xlxwtpQZNWLwXySGUaOEpFZ1HKT8ClJvyyWsnI0tXDxVWD6/TNrsKMpiPJ7QjxwP1gQ7Kt17ChUs10gYXCC2yBY1VmGLQtjhgQVwuS8lTmG0/tdkMe10ld5HNGfCJYINxZfxQA+69NWb8OmNnxKYbKf7+3s9+OSAlQ5zpTLcnr2/1aBJMugHpyHWW0YT2vJs2vH7HOesVVvDeTqB9EaqbnJera62bAG6jgu3BSSSSpD0OvbwdTW4LI/3AqqflbwsRZG+eheRBxH0bPxJF/eHaNo5sl4oQ9HzIr5loQJkcY8bFJbkyFEcmjmXSzbLbcND8+9OzsmKZxY7qu4J1WiYMMw3i7d/r2x9KMI+f47tQfrwelca8MJNN4dbsUluxd9ffsThF4cjFR6BKTEvJhq8js0uzAi5IO/9Zpf2+A6fP7Ehc+P4Uao7E8SRWDs8VG47H33b2QXkvtfHD6QQwrzg4wgHkNsVHeE/6g6aISbA/ERAsjME8FvChhnAlXhCa8v2UCnQhAwvLjZcZbH73cg8ieGCxveiJQ3ewApNju7+6F7Qy3pLX2If43NAtVyPVtpo8p9rapI9qMeh8xk5QsKolGlGkrO6jwrOumYPW57nPgYMIIo30oS8qzv/xsPlH25cNUEByctTmvNzfNv5P68U80Zuhlaic5/5b9INaeSsGHcciXjqtNqoWUbSBrR8JnnuP3tOJ6P6NXqgivwfbEsUh9d1ZJXLOW5UfBCgbtpbENtryiJCpnUtT3U3XvSvZolC9pQWCLLYWENsq8xWL4IDj5l3AnqAe5EIbPdTUBhkQAJqXd5VjBCsbPdxpL6CO1cBYk29MMPjgOhKJ4i34QTkv9c96IzI5/SAXYUDOC7Ffc3QKtlY8x2d/3qNZrLWPxH9e5QBLLhyhykq8zjT2g97YYL7YITWaapi/LItNH3ro9jbeYtmeluUU9MO+G6fOhoQNFlyIk3oP/iNmy34v7rib/0imEE3vnRTXomV7msMO1CLGzdDZ6plibe9CCYWrQFvy8us9HrPq9wrylZ29CWeSz1hV2wSffEOfT7me9q6tP3D4tA6yhNUlC4tL6T2brdzDZb/oDZFIrHmHxO6C4xByxYxinwgydTGyzjBOqPc8nbnQXd+6vqnI2wCeenOs/hz3EGVVqEXDrJ+hu05vHQmdcbEHg/vHYj/bq4utngVXy25Wgy2XhtqaSqLEYneYnYuFXnVtYWcFg7PsFq58pmgCs1eqeuflMOig6EJB7dyQrWWLyaZiLI1o/LBu47H6qs/y6jEOyAiRCorNlkTj8zPh676W6sbREDM9OrJJ78Rf8woZEvEH5XIy4K3/Xrfj2fX21pO9EfsHI+77Ni/jlCLNNm9IOtkHTGcujFVmuKGCWsuNmwSHvSiLIVxTxYU+cJIaB6yR4WvERwc4TpsW7vF6l7TSegfS6QTHSswc8b8s4ixBuh6mXDyyVBvf11EYoSgj+fgPDmPCI/LNybiKzqZ5XERaz12FmnoD8cJAgueofGM2m3L1BfYFrwCM0Y+B53iapkmfeZbnr/B2d3DGfEqHBFDd7hf+TNA1gNqGguHXfMW0k4O9MYXzzwryxTxqADFvlG5tuqnxhWzn1sJKnJosBYyJfzMs05Z1w1e4/NnOy7md7rI5jyD0H6LZ//Vk4N8H11owgpkPBLWKCYt0CH//fZGvdKEAZCTAWk0ZLTo1oDowNUshANBtDW6+NGBijCdS2ZkVa4PoRBEBdBSdJlD8An3CNzkQyQgGZpWrAUzig7IrkQf/ii/ADvBbo42WXxDM8pU8yAMvL4xuF2k3Yo8FTx2QSXH8AkCsZsIzDMr0iqRpUhTDbulH5rIAR0HEgbJ+F4m+HBl+hfIlvXgoxHnJ79Z1IG97rSr39lCEIkki0DvmIMYWXqdt4Zg5by3YHxF4jBIBGflauGXPRbcBZEz6wX+ockzDS2l+NOHqkPInUbgjpFoW1vyk3etEIaW4kNuCbL2sOrbxIz2MvHqxIKwRak+xreNADX3gDemfAvxzBch2y7qqQgOwUPfRdztcaXu6OZpwN0tK5uLzkAxlLlI2Etmmn8ikNVT5l9vutcgZf6LhgMtfxmxOwtMTJf0bTStjfMzGcTjDLZ2f2glcX3rRev3FzTiwEoo4YVleY947OWig8jikSvxu5uYzdgwLbRAtSB7Z48uvf7DAvKlOzvgDPazppOBCHP0G+X/rdnlBC0LB8WZVh8yh72OdbVB0YqW1WXqz574qrprGetsDRe/7G8VThGlIcLoD3MuwmQBItgurYs/609v4NZjllzJ8Vug0dbz1God01/GJTMPujM71EKw4LStPnLG9ppJ5Mvg8cq+JYi+lWfQz988h8iaF0pUq6Szzd/gAKur9SrM5s41K0PVk+vKDtK0XTfN+DdFxsdy7TRKyU1mU1kOBrqFuDEWXgBY0vASP6kxHCLwOpf0yZdVT0FcuoJoJ26V5ctplr+n9u/dJ1Nd5sO6Pq+BDzkpFQTVpAct95BAyjhTPJZ3QF+pxCLMbC+5vWbWc8GSeqUhrAZeCNvB3beB1eu1dda4l1EIqGxk08VhWELyV4FGonGLH2+8NBwY/utspvKEpk5rJVPq7x5VJR36fo/Lj0HO4ZnmmPsgS9iHcA0o+vubXAUssEMcj5jhVBRaqRn8EkCz+6atTi3wF2k1eRa2m73ifn4oFXpGPc9qOLgvOwen91anC9RlVKlRXH3/yN3xAw45Prw2NteLylamGPwPZ5cjluWWgdFZ5Z68EaZjqy7JeLP2h6pntoRoa1rPvbTUhJSkP22QElN/llin+Q5H1nSoHQsqyPDDC1YnCAS6smfR3laxXRIXvp8L3FLU2eDSEedWbvrm5p5L0Z26oG5T/9arojl6W7yWEsNXJtvxjoVe6kQEFfEP2eX0cgV57WJt3Wizn+/cN2cdk4HDdvGY8lwat3iHZjKIqCpqwBEM4Y85nRsLpYkP3LvQ7r+ACL36ifZ/j1uMkgqcy3IaR2A6PQ+9Bv6mb5NgYCJ5QEevTAkOH1t9B3sxorx0RZnG0thpA6z1a4dBFjT7HokvD2A687ja8dHZGK6qYhzk3/baLC9rB7XHaRO+tb9ls3iUjMGc2qe3gKEMx1VcmE7nCzsRPa26Le6bUbdLDeH5Sc0Jl22WlLmtE0NYWAVjeSINeVAlFB3XLTZBH2kqClMa+sETBQwdEaMgGxArsQT5Lrvk4+tnEUdq1fO7I49USKUii7WXmnvc6rstW2OfCefxeCr6rZxb1qtBqaw4LPpwiRg1XmyZGV7WBWe7USFWiqHpBOsIllJlbUgWkiHLNGIOl/5y2a2PSpbp9MMFei2oU8Oye+XIz10RcW8GUWQGapyGFv70CAhVQg5fQ0MTS7HfZbOQ/Ujh1gHEnGoOsjqXECp8axnlmmXCuqUi1Y9LdI3XFSsvXM/e6VLqujEKJwFxNzZS1Rzmr58MfGWcIai/5zyzqom9tobRPAkgAzjGgV/KCz6c0iHweV7ek+u/IEOP/4rGTPGd6y6eHjdEPy4lP4k79blvt7ZzGDeZkiPhNHkYDMbFkhpEohDdJ23DUvZ8AHMK2q7mc8k2ngEw1WTXhJyYaqCm9UMwv3b+ct1xwX7XEX6wAAAAAAA',
    'data:image/webp;base64,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'
])

const audio = ref([
    {
        chinese: 'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/eb67de95c3fa11781fb96cd7e4deceb6_4289111023184811496.png',
        english:'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/16d3ac84953c0e1722e5c0bc29d09c55_5853306198839740376.png',
    },
    {
        chinese:'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/5d3e75e9e428bc19e4e8aa6ecab781b1_8131800421687467985.png',
        english:'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/2ae9c2c7fca8541039bb96a00cfe826d_4523771632367567327.png',
    },
    {
        chinese:'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/0d85743842060731a758109e4f082ee9_3279063433041294242.png',
        english:'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/c49d831f4b68e597e15e3727d7257fb2_8976966752182571014.png'
    },
    {
        chinese:'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/660a87707c93b5e52cde421276607df2_1303846047091472420.png',
        english:'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/916f968be031a496fd1888ec1abd28f2_7553049125532209507.png'
    },
    {
        chinese:'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/7e65a893de2fcc5dba4706d86181ed72_4423961159681951529.png',
        english:'https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/09/23/76551145fd57e7f8f4e5436250111690_3089605828674088702.png'
    }
    
])

const videoHideEffect = ref<number[]>([0])
const videoHide = ref<string[]>(['none'])
const videoShow = ref<boolean[]>([false])

const emit = defineEmits(["videoId"]); //当点击某个部件时发送给父组件以禁用swiper（不能滚动到下一页或上一页）

let mw = ref(true);

const video4ClickIn =(index:number) => {
    const prev:any = document.getElementById('prev')
    const next: any = document.getElementById('next')
    const p4pag: any = document.getElementById('p4pag')

    prev.style.setProperty('z-index', '0')
    next.style.setProperty('z-index', '0')
    p4pag.style.setProperty('opacity', '0.3')
    // p4pag.style.setProperty('background-color', 'rgba(0, 0, 0, 0.7)')
    videoShow.value[index] = true;
    videoHide.value[index] = "block";
    mw.value = false;
    emit("videoId", mw.value);
    swiperCopy.autoplay.stop();
    setTimeout(() => {
        videoHideEffect.value[index] = 1;
    }, 10);
}

const videoClickOut = (index: number) => {
    const prev:any = document.getElementById('prev')
    const next: any = document.getElementById('next')
    const p4pag: any = document.getElementById('p4pag')

    prev.style.setProperty('z-index', '1')
    next.style.setProperty('z-index', '1')
    p4pag.style.setProperty('opacity', '1')
    videoHideEffect.value[index] = 0;
    mw.value = true;
    emit("videoId", mw.value);
    swiperCopy.autoplay.start();
    setTimeout(() => {
        videoHide.value[index] = "none";
        videoShow.value[index] = false;
    }, 300);
};

const player4HI =() => {
    player4Bg.value = playerClick.value
}

const player4HO = () => {
    player4Bg.value = player.value
}

const pagination = ref<any>({
    el: '.swiper-pagination4',
    // clickable: true,
    type: 'custom',
    renderCustom: function (swiper: any, current: number, total: number) {
        var paginationHtml = "";
        for (var i = 0; i < total; i++) {
            // 判断是不是激活焦点，是的话添加active类，不是就只添加基本样式类
            if (i === (current - 1)) {
                // console.log("total:", current, total);
                // paginationClick(i)
                pag4inationActive(i)
            }
        }
        return paginationHtml;
    }
},) 



var swiperCopy:any = ref()
const onSwiper = ((swiper: any) => {
    swiperCopy = swiper
}) 

// const temp = p4Paginations.value
const paginationClick = (index: number)=>{
    // console.log(index);
    swiperCopy.slideTo(index+1, 100, false);
    pag4inationActive(index)
}

const pag4inationActive = (index: number) => {
    for (let i = 0; i < p4Paginations.value.length; i++) {
        p4Paginations.value[i] = temp.value[i]
    }
    p4Paginations.value[index] = p4PaginationsSel.value[index]
}

</script>

<style scoped>
.swiper {
    width: 100vw;
    height: 100vh;
}

.swiper-slide {
    background-position: center;
    background-size: cover;
    background: transparent !important;
    z-index: 1;
}

.swiper-slide .bg {
    width: 100%;
    height: 100%;
}

.videoDetal4 {
    position: absolute;
    top: 0;
    width: 100vw !important;
    height: 100vh !important;
    background-color: rgba(0, 0, 0, 0.7);
    align-content: center;
    vertical-align: center;
    transition: all 0.3s;
    z-index: 1;
}

.videoDetal4 .videoDetal-bg4 {
    position: absolute;
    width: 456px;
    height: 256px;
    top: 200px;
    left: 450px;
    object-fit: contain;
}

 .swiper-slide .content {
    position: relative;
    top: 130px;
    /* top: 0px; */
    left: 520px;
    width: 59px;
    height: 59px;
}

.swiper-slide .bg .audiostylec {
    position: relative;
    top:330px;
    /* top: 0px; */
    left: 333px;
    width: 164px;
    height: 51px;
}

.swiper-slide .bg .audiostylee {
    position: relative;
    top: 335px;
    /* top: 0px; */
    left: 333px;
    width: 164px;
    height: 51px;
}

/* .custom-pagination{
    position: absolute;
    width: 400px;
    height: 40px;
    top:600px;
    left: 300px;
    display: flex;
    z-index: 100;
} */
.paginations {
    position: absolute;
    top: 580px;
    left: 492px;
    display: flex;
    align-content: center;
    opacity: 1;
    z-index: 1;
}

.swiper-button-prev {
    position: absolute;
    left: 190px;
    top: 315px;
    width: 98px;
    height: 102px;
    outline: none;
    z-index: 1;
}
.swiper-button-next{
    position: absolute;
    right: 190px;
    top: 315px;
    width: 98px;
    height: 102px;
    z-index: 1;
}
</style>