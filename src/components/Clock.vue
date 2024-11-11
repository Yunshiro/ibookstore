

<script lang="js" setup>
import { onMounted, ref } from 'vue'

// currentTime show the time in templates.
let currentTime = ref("")

// get current time
function getCurrentTime() {
  const currentDate = new Date()

  // get hours, minus, seconds
  const hours = currentDate.getHours()
  const minus = currentDate.getMinutes()
  const seconds = currentDate.getSeconds()

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
