<template>
  <div>
    <div>Ngày sinh: {{dateValue}}</div>
    <input type="date" v-model="dateValue">
  </div>
</template>

<script setup>
import {ref} from "vue"
    const dateValue = ref("")
</script>

<style>

</style>