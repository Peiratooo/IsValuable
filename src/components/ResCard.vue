<template>
    <a href="https://space.bilibili.com/7277347" target="_blank" class="resCard" :class="objClass">
        <div class="title">{{ outPut }}</div>
        <div class="resData">你的工作性价比: {{ resData.toFixed(2) }}</div>
        <img src="https://mcfun.oss-cn-shenzhen.aliyuncs.com/isValuable/line.png" alt="" class="line">
    </a>
</template>

<script setup>
const props = defineProps({
    outPut: {
        type: String,
    },
    resData:{
        type:Number,
    },
    objClass:{
        type:Object,
    }
});
</script>

<style scoped>
.resCard {
    display: flex;
    flex-direction: column;
    width: 60%;
    margin: 70px auto;
    align-items: center;
    border-radius: 20px;
    box-shadow: 7px 7px 20px #e8e8e8, -7px -7px 20px #e0e0e0;
    max-width: 500px;
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
    border-bottom: #ffffff23 1px solid;
}
.resData {
    margin-top: 15px;
    margin-bottom: 25px;
    font-size: 22px;
}
.bad {
    background: rgb(100, 100, 100);
background: linear-gradient(312deg, rgb(100, 100, 100) 0%, rgba(255,255,255,1) 71%);
}
.normal {
    background: rgb(206,255,225);
background: linear-gradient(312deg, rgba(206,255,225,1) 0%, rgba(255,255,255,1) 68%);
box-shadow: 7px 7px 20px rgba(206,255,225,1);

}
.great {
    background: rgb(255, 226, 206);
background: linear-gradient(312deg, rgb(255, 230, 189) 0%, rgba(255,255,255,1) 71%);
box-shadow: 7px 7px 20px rgba(255, 226, 206,0.5);
}
</style>