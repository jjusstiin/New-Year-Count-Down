<template>
  <div class="container">
    <div class="title">
      New Year count Down
    </div>
    <div class="timer">
      <Timer :count="remainingDays" label="Days"/>
      <Timer :count="remainingHours" label="Hours"/>
      <Timer :count="remainingMinutes" label="Minutes"/>
      <Timer :count="remainingSeconds" label="Seconds"/>
    </div>
  </div>
</template> 

<script setup lang="ts">
import { defineComponent, onMounted, onUnmounted, ref } from 'vue';
import Timer from '@/components/Timer.vue';
import { log } from 'console';
  
const newYears = "1 jan 2023 00:00:00";
const remainingDays = ref("")
const remainingHours = ref("")
const remainingMinutes = ref("")
const remainingSeconds = ref("")

function countDown(){
  const newYearsDate: Date = new Date(newYears);
  const currentDate: Date = new Date();
  const totalSeconds = (newYearsDate.getTime() - currentDate.getTime()) / 1000;

  const days = Math.floor(totalSeconds / 3600 / 24);
  const hours = Math.floor(totalSeconds / 3600) % 24;
  const mins = Math.floor(totalSeconds / 60) % 60;
  const seconds = Math.floor(totalSeconds) % 60;
  
  remainingDays.value = setTime(days);
  remainingHours.value = setTime(hours);
  remainingMinutes.value = setTime(mins);
  remainingSeconds.value = setTime(seconds);
}

function setTime(value:number){
  return value < 10 ? `0${value}` : value.toString();
}

let timeInterval: ReturnType<typeof setInterval>;
onMounted(()=>{
  timeInterval = setInterval(countDown, 1000)
})

onUnmounted(()=>{
  clearInterval(timeInterval);
})

</script>

<style lang="scss" scoped>
.container{
  position: relative;
  height: 100vh;
  background-image: url("@/assets/bg.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center center;
  color: #2f4f5d;
  text-align:center;

  .title{
    padding-top: 30px;
    font-size: 5rem;
    font-weight: bold;
  }

  .timer{
    padding-top: 20px;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }
}
</style>
