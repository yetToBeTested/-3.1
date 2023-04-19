<template>
    <div class="bg" style="background: center center / cover no-repeat; overflow: hidden; position: relative; width: 100%; height: auto; font-size: 60.8333px;">
        <div class="text">
                <P>&nbsp&nbsp&nbsp&nbsp学习资料在学校，可我进不去啊...</P>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const show = ref("none")
const dream =() => {
    console.log("aaa");
    show.value = "block";
}
</script>

<style scoped>
.bg{
    background-color: black;
}

.bg .text{
    width: 100%;
    height: 100%;
    line-height: 100%;
    align-items: center;
    color: rgb(97, 93, 93);
}
</style>