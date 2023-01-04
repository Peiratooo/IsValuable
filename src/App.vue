<script setup>
import Question from "./components/Question.vue";
import Info from "./components/Info.vue";
import ResCard from "./components/ResCard.vue";
import { reactive, toRefs, onMounted, ref, provide, watch } from "vue";
const userData = reactive({
  data: {
    dailySalary: {
      value: "",
      changed: false,
    },
    workingHours: {
      value: "",
      changed: false,
    },
    commutingHours: {
      value: "",
      changed: false,
    },
    funHours: {
      value: "",
      changed: false,
    },
    education: {
      value: "",
      changed: false,
    },
    environment: {
      value: "",
      changed: false,
    },
    oppositeSex: {
      value: "",
      changed: false,
    },
    colleague: {
      value: "",
      changed: false,
    },
    isEarly: {
      value: "",
      changed: false,
    },
    city: {
      value: "",
      changed: false,
    },
    holiday: {
      value: "",
      changed: false,
    },
    overtime: {
      value: "",
      changed: false,
    },
  },
});
let objClass = reactive({
  bad: false,
  normal: false,
  great: false,
});
let outPut = ref("");
let isFinished = ref(false);
let res = ref(0);
let showInfo = ref(false);
let showRes = ref(false);
function calData(userData) {
  res.value = 
    Math.sqrt(
      (userData.dailySalary.value *
        parseFloat(userData.environment.value) *
        parseFloat(userData.oppositeSex.value) *
        parseFloat(userData.colleague.value) *
        parseFloat(userData.holiday.value) *
        parseFloat(userData.isEarly.value) *
        parseFloat(userData.overtime.value)) /
        (25 *
          (userData.workingHours.value +
            0.5 * userData.commutingHours.value -
            0.5 * userData.funHours.value) *
          parseFloat(userData.education.value) *
          parseFloat(userData.city.value))
    )
  ;
}
function changeShowInfo() {
  showInfo.value = !showInfo.value;
}
watch(userData.data, () => {
  let count = true;
  for (var key in userData.data) {
    if (!userData.data[key].changed) {
      count = false;
      // console.log(key);
    }
  }
  if (count) {
    isFinished.value = true;
  }
});
function changeShowRes() {
  calData(userData.data);
  showRes.value = true;
  if (res.value < 0.8) {
      outPut.value = "惨爆";
      objClass.bad = true;
    } else if (0.8 <= res.value && res.value < 0.9) {
      outPut.value = "惨";
      objClass.bad = true;
    } else if (0.9 <= res.value && res.value < 1.2) {
      outPut.value = "平淡";
      objClass.normal = true;
    } else if (1.2 <= res.value && res.value <= 1.5) {
      outPut.value = "爽";
      objClass.great = true;
    } else {
      outPut.value = "爽爆";
      objClass.great = true;
    }
}
</script>

<template>
  <div
    @click="changeShowInfo()"
    v-if="!showInfo && !isFinished"
    class="infoButton"
  >
    ?
  </div>
  <Info v-show="showInfo" class="info"></Info>
  <div @click="changeShowInfo()" v-show="showInfo" class="mask"></div>
  <div @click="changeShowRes()" v-if="isFinished && !showRes" class="run">
    这班上得值不值？！
  </div>
  <div v-if="!showRes" class="container">
    <Question :userData="userData"></Question>
  </div>
  <ResCard
    v-if="showRes"
    :outPut="outPut"
    :resData="res"
    :objClass="objClass"
  />
</template>

<style scoped>
.container {
  display: block;
  width: 80%;
  margin: 50px auto;
  max-width: 800px;
  margin-bottom: 150px;
}

.run {
  position: fixed;
  z-index: 999;
  left: 0;
  right: 0;
  bottom: 5%;
  width: 68%;
  text-align: center;
  background-color: #363636;
  border-radius: 10px;
  padding: 20px;
  color: #fff;
  margin: 0 auto;
  font-size: 22px;
  letter-spacing: 0.2rem;
  box-shadow: 0px 10px 37px rgba(0, 0, 0, 0.2);
  max-width: 700px;
}

.run:hover {
  cursor: pointer;
}

.infoButton {
  height: 50px;
  width: 50px;
  border-radius: 50px;
  background: #ffffff;
  box-shadow: 0px 5px 10px #bcbcbc;
  border-radius: 100%;
  text-align: center;
  position: fixed;
  bottom: 10%;
  right: 15%;
  z-index: 99;
  font-size: 35px;
  cursor: pointer;
  color: #555;
}

.info {
  position: fixed;
  z-index: 9;
  margin: 0 auto;
  left: 0;
  right: 0;
}

.mask {
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 8;
  background-color: rgba(0, 0, 0, 0.2);
  backdrop-filter: blur(5px);
  -webkit-backdrop-filter: blur(5px);
  box-shadow: rgba(142, 142, 142, 0.19) 0px 6px 15px 0px;
  -webkit-box-shadow: rgba(142, 142, 142, 0.19) 0px 6px 15px 0px;
  color: rgba(67, 67, 67, 0.75);
}
</style>
