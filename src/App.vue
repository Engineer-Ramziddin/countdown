<script setup lang="ts">
import Countdown from './components/Countdown.vue'

const defaultDate = '2024/06/01'

function getUntilDate() {
  const param = new URL(location.href).searchParams.get('until') || defaultDate
  if (/\d{8}/.test(param))
    return `${param.substring(0, 4)}/${param.substring(4, 6)}/${param.substring(6, 8)}`
  return defaultDate
}

const until = getUntilDate()
</script>

<template>
  <!-- <Countdown :until="until" /> -->
  <h1>Salom Musobek</h1>
</template>

<style>
h1 {
  color: #fff;
  font-size: x-large;
  font-family: 'Times New Roman', Times, serif;
}
</style>
