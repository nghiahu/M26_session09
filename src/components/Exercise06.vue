<template>
  <div>
    <div>Sở thích: {{hobbiesValue}} </div>
        <input type="checkbox" value="Code" v-model="hobbiesValue" name="hobbies"> Code <br>
        <input type="checkbox" value="Đá bóng" v-model="hobbiesValue" name="hobbies"> Đá bóng <br> 
        <input type="checkbox" value="Game" v-model="hobbiesValue" name="hobbies"> Game
  </div>
</template>

<script setup>
import {ref} from "vue"
    const hobbiesValue = ref([])
</script>

<style>

</style>