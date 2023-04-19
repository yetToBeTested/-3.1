<template>
    <!-- :style="{ width: wp7Footer, left: lp7Footer }" -->
    <div class="p7Footer" >
        <!-- 四个图标 -->
        <img ref="footerIcon" @click="iconClick(item.id)" 
        :id="'fotterIconBg' + item.id" class="fotterIconBg"
        v-for="item in footerIcons" :key="item.id" :src="item.url" 
        alt="" draggable="false" />
    </div>
</template>

<script setup lang="ts">
import { onUnmounted, onMounted, ref } from "vue";

let footerIcon = ref(null);
const emit = defineEmits(["vxOpen"]);

// 底下图片数据
let footerIcons = ref([
    {
        id: 0,
        url: "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/08/16/dc0d738971ce14760fa22302739589b7_6184953676476702286.png",
    },
    {
        id: 1,
        url: "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/08/16/b1eb003f78ccfc7b8eb6fda11279a588_2042388589199221716.png",
    },
    {
        id: 2,
        url: "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/08/16/85e3fb1e13e295daf89762afefe06601_5142091714308898800.png",
    },
    {
        id: 3,
        url: "https://uploadstatic.mihoyo.com/puzzle/upload/puzzle/2022/08/16/7f8e77a962599583d0678de9141791e7_5887176268253724597.png",
    },
]);
let iconLink = ref([
    { id: 0, url: "https://weibo.com/ysmihoyo" },
    { id: 2, url: "https://space.bilibili.com/401742377/" },
    { id: 3, url: "https://bbs.mihoyo.com/ys" },
]);

// 当点击各个图片对应事件
const iconClick = (id: number) => {
    if (id > 1) {
        window.open(iconLink.value[id - 1].url);
    } else if (id < 1) {
        window.open(iconLink.value[id].url);
    } else {
        console.log("open");
        emit("vxOpen", true);
    }
};

</script>

<style scoped>
.p7Footer {
    position: absolute;
    width: 425px;
    display: flex;
    align-content: center;
    left: 466px;
    /* left: 0; */
    height: 100%;
    /* background-color: rgba(255, 0, 0, 0.1); */
}

.fotterIconBg {
    height: 100%;
}

.fotterIconBg:nth-child(1) {
    margin-right: 55px;
    height: 100%;
}

.fotterIconBg:nth-child(2) {
    margin-right: 40px;
    height: 100%;
}

.fotterIconBg:nth-child(3) {
    margin-right: 43px;
    height: 100%;
}

.fotterIconBg:nth-child(4) {
    margin-right: 0px;
    height: 100%;
}
</style>