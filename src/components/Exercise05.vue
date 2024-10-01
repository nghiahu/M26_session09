<template>
  <div>
    <div>Giới tính: {{genderValue}} </div>
        <input type="radio" value="Nam" v-model="genderValue" name="gender"> Nam <br>
        <input type="radio" value="Nữ" v-model="genderValue" name="gender"> Nữ <br> 
        <input type="radio" value="Khác" v-model="genderValue" name="gender"> Khác
  </div>
</template>

<script setup>
import {ref} from "vue"
    const genderValue = ref("")
</script>

<style>

</style>