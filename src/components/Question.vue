<template>
    <div class="question">
        <div class="content">
            <div class="text">平均日薪</div>
            <div class="answer">
                <input @input="setChanged(userData.data, 'dailySalary')" v-model="userData.data.dailySalary.value"
                    type="number" placeholder="请输入数字"/>
                <div class="other">单位:元(你又不是某爽)</div>
            </div>
        </div>
        <img src="../assets/cash.png"  style="transform: rotate(30deg); right:-50px;" alt="" class="deco" />
    </div>
    <div class="question">
        <div class="content">
            <div class="text">工作时长</div>
            <div class="answer">
                <input @input="setChanged(userData.data, 'workingHours')" v-model="userData.data.workingHours.value"
                    type="number"  placeholder="请输入数字"/>
                <div class="other">下班时间-上班时间</div>
            </div>
        </div>
        <img style="height: 150px; right: -25px; bottom: -30px" src="../assets/work.png" alt="" class="deco" />
    </div>
    <div class="question">
        <div class="content">
            <div class="text">通勤时常</div>
            <div class="answer">
                <input @input="setChanged(userData.data, 'commutingHours')" v-model="userData.data.commutingHours.value"
                    type="number"  placeholder="请输入数字"/>
                <div class="other">上下班来回时长</div>
            </div>
        </div>
        <img style="height: 135px; right: -10px; bottom: -20px" src="../assets/subway.png" alt="" class="deco" />
    </div>
    <div class="question">
        <div class="content">
            <div class="text">摸鱼时常</div>
            <div class="answer">
                <input @input="setChanged(userData.data, 'funHours')" v-model="userData.data.funHours.value"
                    type="number"  placeholder="请输入数字"/>
                <div class="other">不干活+吃饭+午休</div>
            </div>
        </div>
        <img style="
        height: 150%;
        right: -15px;
        bottom: -25px;
        transform: rotate(-120deg);
        transform: scale(-1, 1);
      " src="../assets/fish.png" alt="" class="deco" />
    </div>
    <div class="sradio">
        <div class="radioContent">
            <div class="text">学历系数</div>
            <div class="radios" @input="setChanged(userData.data, 'education')">
                <div class="item">
                    <input type="radio" value="0.9" v-model="userData.data.education.value" /><label>专科及以下</label>
                </div>
                <div class="item">
                    <input type="radio" value="1" v-model="userData.data.education.value" /><label>普通本科</label>
                </div>
                <div class="item">
                    <input type="radio" value="1.1" v-model="userData.data.education.value" /><label>211/985本科</label>
                </div>
                <div class="item">
                    <input type="radio" value="1.6" v-model="userData.data.education.value" /><label>普通硕士</label>
                </div>
                <div class="item">
                    <input type="radio" value="1.8" v-model="userData.data.education.value" /><label>211/985硕士</label>
                </div>
                <div class="item">
                    <input type="radio" value="2" v-model="userData.data.education.value" /><label>普通博士</label>
                </div>
                <div class="item">
                    <input type="radio" value="2.4" v-model="userData.data.education.value" /><label>211/985博士</label>
                </div>
            </div>
        </div>
        <img style="height: 120px; right:-20px; bottom: -30px" src="../assets/edu.png" alt="" class="deco" />

    </div>
    <div class="sradio">
        <div class="radioContent">
            <div class="text">城市系数</div>
            <div class="radios" @input="setChanged(userData.data, 'city')">
                <div class="item">
                    <input type="radio" value="1.1" v-model="userData.data.city.value" /><label>一线城市</label>
                </div>
                <div class="item">
                    <input type="radio" value="1.05" v-model="userData.data.city.value" /><label>强二线线城市</label>
                </div>
                <div class="item">
                    <input type="radio" value="1" v-model="userData.data.city.value" /><label>二线城市</label>
                </div>
                <div class="item">
                    <input type="radio" value="0.9" v-model="userData.data.city.value" /><label>三线城市及以下</label>
                </div>
            </div>
        </div>
        <img style="height: 120px; right:0px; bottom: -20px; transform: rotate(0deg);" src="../assets/city.png" alt="" class="deco" />

    </div>
    <div class="sradio">
        <div class="radioContent">
            <div class="text">工作环境系数</div>
            <div class="radios" @input="setChanged(userData.data, 'environment')">
                <div class="item">
                    <input type="radio" value="0.85"
                        v-model="userData.data.environment.value" /><label>偏僻的地区，郊区的工厂/工地/艰苦户外等工作环境</label>
                </div>
                <div class="item">
                    <input type="radio" value="0.9"
                        v-model="userData.data.environment.value" /><label>工厂/工地/户外等工作环境</label>
                </div>
                <div class="item">
                    <input type="radio" value="1.05"
                        v-model="userData.data.environment.value" /><label>CBD/体制内等工作环境</label>
                </div>
            </div>
        </div>
        <img style="height: 120px; right:0px; bottom: -20px; transform: rotate(0deg);" src="../assets/env.png" alt="" class="deco" />

    </div>
    <div class="sradio">
        <div class="radioContent">
            <div class="text">异性环境系数</div>
            <div class="radios" @input="setChanged(userData.data, 'oppositeSex')">
                <div class="item">
                    <input type="radio" value="0.98"
                        v-model="userData.data.oppositeSex.value" /><label>周围好看的异性很少</label>
                </div>
                <div class="item">
                    <input type="radio" value="1" v-model="userData.data.oppositeSex.value" /><label>周围好看的异性不多不少</label>
                </div>
                <div class="item">
                    <input type="radio" value="1.02"
                        v-model="userData.data.oppositeSex.value" /><label>周围好看的异性很多</label>
                </div>
            </div>
        </div>
        <img style="height: 120px; right:-20px; bottom: -20px" src="../assets/sex.png" alt="" class="deco" />

    </div>
    <div class="sradio">
        <div class="radioContent">
            <div class="text">同事环境系数</div>
            <div class="radios" @input="setChanged(userData.data, 'colleague')">
                <div class="item">
                    <input type="radio" value="0.98" v-model="userData.data.colleague.value" /><label>SB很多</label>
                </div>
                <div class="item">
                    <input type="radio" value="1" v-model="userData.data.colleague.value" /><label>基本上是正常人</label>
                </div>
                <div class="item">
                    <input type="radio" value="1.02" v-model="userData.data.colleague.value" /><label>大佬很多</label>
                </div>
            </div>
        </div>
        <img style="height: 110px; right:0px; bottom: -20px;transform: rotate(0deg);" src="../assets/colleage.png" alt="" class="deco" />

    </div>
    <div class="sradio">
        <div class="radioContent">
            <div class="text">休息日系数</div>
            <div class="radios" @input="setChanged(userData.data, 'holiday')">
                <div class="item">
                    <input type="radio" value="0.95" v-model="userData.data.holiday.value" /><label>大小周</label>
                </div>
                <div class="item">
                    <input type="radio" value="0.9" v-model="userData.data.holiday.value" /><label>单休</label>
                </div>
                <div class="item">
                    <input type="radio" value="1" v-model="userData.data.holiday.value" /><label>双休</label>
                </div>
                <div class="item">
                    <input type="radio" value="1.05" v-model="userData.data.holiday.value" /><label>双休以上</label>
                </div>
                <div class="item">
                    <input type="radio" value="0.85" v-model="userData.data.holiday.value" /><label>月休3日</label>
                </div>
                <div class="item">
                    <input type="radio" value="0.8" v-model="userData.data.holiday.value" /><label>月休2日及以下</label>
                </div>
            </div>
        </div>
        <img style="height: 120px; right:-30px; bottom: -20px" src="../assets/relax.png" alt="" class="deco" />

    </div>
    <div class="sradio">
        <div class="radioContent">
            <div class="text">上班时间系数</div>
            <div class="radios" @input="setChanged(userData.data, 'isEarly')">
                <div class="item">
                    <input type="radio" value="0.95" v-model="userData.data.isEarly.value" /><label>早上8点左右上班</label>
                </div>
                <div class="item">
                    <input type="radio" value="1" v-model="userData.data.isEarly.value" /><label>早上9点左右上班</label>
                </div>
                <div class="item">
                    <input type="radio" value="1.05" v-model="userData.data.isEarly.value" /><label>早上10点以后上班</label>
                </div>
            </div>
        </div>
        <img style="height: 120px; right:-20px; bottom: -20px" src="../assets/time.png" alt="" class="deco" />

    </div>
    <div class="sradio">
        <div class="radioContent">
            <div class="text">下班后工作系数</div>
            <div class="radios" @input="setChanged(userData.data, 'overtime')">
                <div class="item">
                    <input type="radio" value="0.95" v-model="userData.data.overtime.value" /><label>下班后偶尔少量义务加班</label>
                </div>
                <div class="item">
                    <input type="radio" value="1" v-model="userData.data.overtime.value" /><label>下班后不怎么加班</label>
                </div>
                <div class="item">
                    <input type="radio" value="0.85" v-model="userData.data.overtime.value" /><label>下班后经常较多义务加班</label>
                </div>
            </div>
        </div>
        <img style="height: 120px; right:-20px; bottom: -20px" src="../assets/overtime.png" alt="" class="deco" />

    </div>
</template>

<script setup>
import { reactive, toRefs, watch } from "vue";
const props = defineProps({
    userData: {
        type: Object,
    },
});
function setChanged(userData, tag) {
    if (userData[tag].changed != true) {
        userData[tag].changed = true;
    }
}

</script>

<style scoped>
.question,
.sradio {
    background: #fff;
    border-radius: 20px;
    box-shadow: 7px 7px 20px #e8e8e8, -7px -7px 20px #ffffff;
    color: #333;
    padding: 25px;
    font-size: 22px;
    max-width: 100%;
    margin-bottom: 25px;
    position: relative;
    overflow: hidden;
}

.content,.item {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
}

.content .text {
    letter-spacing: 0.1rem;
}

.radioContent .text {
    padding-bottom: 15px;
    margin-bottom: 15px;
    border-bottom: #efefef 1px solid;
    letter-spacing: 0.1rem;
}

.item {
    justify-content: left;
    font-size: 16px;
    padding: 3.5px 0;
    position: relative;
}

.item label {
    padding-left: 10px;
    letter-spacing: 0.1rem;
}
.item input {
    margin-top: 2px;
}
.item input::before {
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
}

.radioContent {
    display: flex;
    flex-direction: column;
}

.radios {
    display: flex;
    flex-direction: column;
}

.deco {
    position: absolute;
    height: 200%;
    bottom: -50px;
    right: -20px;
    opacity: 0.035;
    /* transform: rotate(30deg); */
    filter: saturate(0%);
}

.text {
    width: 100%;
}

.answer {
    z-index: 5;
    min-width: 5rem;
    top: 12px;
    /* max-width:100%; */
    display: flex;
    flex-direction: column;
    align-items: center;
}

.other {
    font-size: 8px;
}

.answer input {
    color: #353535;
    text-decoration: none;
    background: none;
    border: none;
    border-bottom: #ccc 1px solid;
    width: 100%;
    font-size: 22px;
    text-align: center;
    font-family:'字体圈欣意吉祥宋';
    letter-spacing: 0.1rem;
    
}

.answer input:focus {
    outline: none;
}
</style>
