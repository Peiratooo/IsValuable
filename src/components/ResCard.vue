<template>
    <a href="https://space.bilibili.com/7277347" target="_blank" class="resCard">
        <div class="title">{{ outPut }}</div>
        <div class="resData">你的工作性价比: {{ resData }}</div>
        <img src="../assets/line.png" alt="" class="line">
    </a>
</template>

<script setup>
const props = defineProps({
    outPut: {
        type: String,
    },
    resData:{
        type:Number
    }
});
</script>

<style scoped>
.resCard {
    display: flex;
    flex-direction: column;
    width: 60%;
    margin: 0 auto;
    align-items: center;
    border-radius: 20px;
    box-shadow: 7px 7px 20px #e8e8e8, -7px -7px 20px #e0e0e0;
    max-width: 500px;
    margin-top: 70px;
    padding: 30px;
    justify-content: space-around;
    text-decoration: none;
    color: #333;
}
.line {
    max-width: 100%;
    margin-top: 10px;
    margin-bottom: 15px;
}
.title {
    width: 100%;
    padding-bottom: 35px;
    margin-bottom: 15px;
    text-align: center;
    font-size: 25vh;
    border-bottom: #e8e8e8 1px solid;
}
.resData {
    margin-top: 15px;
    margin-bottom: 25px;
    font-size: 22px;
}
</style>