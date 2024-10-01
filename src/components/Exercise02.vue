<template>
  <div>
    <div>Màu sắc: </div>
    <input type="color" v-model="colorValue">
    <div>
        Mã màu: {{colorValue}}
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue"
    const colorValue = ref("")
</script>

<style>

</style>