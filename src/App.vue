<script setup lang="ts">
import Countdown from './components/Countdown.vue'

// Hozirgi yilning oxiri va keyingi yilning 1-yanvarini avtomatik hisoblash
function getNextYearDate() {
  const now = new Date()
  const nextYear = now.getFullYear() + 1
  return `${nextYear}/01/01`
}

// `until` parametrni olish yoki avtomatik kelasi yilni o'rnatish
function getUntilDate() {
  const param = new URL(location.href).searchParams.get('until')
  if (param && /\d{8}/.test(param))
    return `${param.substring(0, 4)}/${param.substring(4, 6)}/${param.substring(6, 8)}`

  return getNextYearDate()
}

const until = getUntilDate()
</script>

<template>
  <Countdown :until="until" />
</template>

<style>
h1 {
  color: #fff !important;
  font-size: x-large;
  font-family: 'Times New Roman', Times, serif;
}
</style>
