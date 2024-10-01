<template>
  <div>
    <div>Email: </div>
    <input type="text" v-model="emailValue">
    <div>
        Giá trị: {{emailValue}}
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue"
    const emailValue = ref("")
</script>

<style>

</style>