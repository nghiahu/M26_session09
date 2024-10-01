<template>
  <div>
    <div>Tiến độ hoàn thành: {{rangerValue}} %</div>
    <input type="range" v-model="rangerValue">
  </div>
</template>

<script setup>
import {ref} from "vue"
    const rangerValue = ref("")
</script>

<style>

</style>