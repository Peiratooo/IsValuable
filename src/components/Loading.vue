<template>
    <div class="loading" >
        <div class="unv">这班上得值不值？！</div>
        <img data-aos="fade" data-aos-duration="1000" src="../assets/title.png" alt="" class="title">
        <div data-aos="fade" data-aos-duration="1000" data-aos-delay="500" class="loadingThree">
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
        </div>
    </div>
    
</template>

<script setup>

</script>

<style scoped>
.loading {
    height: 100vh;
    width: 100%;
    display: flex;
    background-color: #fff;
    background: linear-gradient(332deg, rgb(255, 253, 250) 0%, rgba(255,255,255,1) 80%);
    align-items: center;
    flex-direction: column;
    position: fixed;
    z-index: 999;
}

.title {
    margin-top: 80px;
    height: 60%;
    opacity: 0.5;
}

.unv {
    position: absolute;
    opacity: 0;
    bottom: 0;
}

.loadingThree {
    width: 100px;
    height: 12px;
    margin-top: 60px;
    display: flex;
    justify-content: space-between;
}

.loadingThree span {
    width: 12px;
    height: 100%;
    border-radius: 100%;
    background: rgb(50, 50, 50);
    animation: load 1.5s ease-out infinite;
}

@keyframes load {
    0% {
        opacity: 1;
    }

    100% {
        opacity: 0;
    }
}

.loadingThree span:nth-child(1) {
    animation-delay: 0.15s;
}

.loadingThree span:nth-child(2) {
    animation-delay: 0.3s;
}

.loadingThree span:nth-child(3) {
    animation-delay: 0.45s;
}

.loadingThree span:nth-child(4) {
    animation-delay: 0.6s;
}

.loadingThree span:nth-child(5) {
    animation-delay: 0.75s;
}
</style>