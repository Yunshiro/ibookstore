

<script lang="js" setup>
import { onMounted, ref } from 'vue'

// currentTime show the time in templates.
let currentTime = ref("")

// get current time
function getCurrentTime() {
  const currentDate = new Date()

  // get hours, minus, seconds
  let hours = currentDate.getHours()
  let minus = currentDate.getMinutes()
  let seconds = currentDate.getSeconds()

  // check the seconds,minus,hours if 0~9, need like the format 00 01 02 03...
  hours = hours < 10 ? "0"+hours : hours
  minus = minus < 10 ? "0"+minus : minus
  seconds = seconds < 10 ? "0"+seconds : seconds

  // time format
  currentTime.value = `${hours}:${minus}:${seconds}`
}

// get time at once on Mounted
onMounted(() => {
  getCurrentTime()
})

setInterval(getCurrentTime, 1000)

</script>

<template>
  <!-- show the time -->
  <h1>Time Now:{{ currentTime }}</h1>
</template>

<style scoped>

</style>
