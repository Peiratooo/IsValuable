<template>
    <div class="infoContainer">
        <div class="title">关 于</div>
        <img class="formula" src="../assets/formula.png" alt="">
        <div class="desc">算法来源: <a class="source" target="_blank"
                href="https://www.zhihu.com/people/la-la-pai-pi-qiu/pins">知乎@天线宝宝烤面包</a></div>
        <div class="article">
           人活着不是为了吃苦的，是为了寻找自己。<br>
           如果你干某一件事，除了痛苦还是痛苦，那就要反思这事值不值得去做了。
        </div>
        <a class="author" href="https://space.bilibili.com/7277347" target="_blank">@Peirato</a>
    </div>
</template>

<script setup>

</script>

<style scoped>
.infoContainer {
    margin: 0 auto;
    width: 68%;
    height: 50vh;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    background: #fff;
    border-radius: 20px;
    /* box-shadow: 7px 7px 20px #e8e8e8, -7px -7px 20px #ffffff; */
    padding: 25px;
    margin-top: 50px;
    max-width: 600px;
}
.formula {
    width: 100%;
}
.title {
    font-size: 22px;
    color: rgba(0,0,0,0.8);
    margin-bottom: 35px;
}
.desc {
    margin: 15px auto;
    font-size: 16px;
}
.article {
    margin-top: 50px;
    font-size: 16px;
}
.author {
    margin-top: 10px;
    width: 100%;
    text-align: center;
    text-decoration: none;
    color: #333;
    padding: 25px 0 5px 0;
}
.source {
    color: #056de8;
}
</style>