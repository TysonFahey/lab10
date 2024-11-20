<script setup>
import BodyMassIndex from './components/BodyMassIndex.vue'

import {ref} from 'vue'

const calculateBMI = (height, weight) => {
  bmi.value = weight / (height * height) 
} // this function calculates the bmi using data we emited in BodyMassIndex.vue

const bmi = ref(0) // Sets the initial bmi to 0 when user loads the page

</script>

<template>
 
<h1>Body Mass Index Calculator</h1>

<BodyMassIndex v-on:user-entered-data="calculateBMI"></BodyMassIndex> <!-- When the user selects calculate, call the calculateBMI function-->

<div>Your BMI is {{ bmi }}</div> <!-- display the users bmi -->
</template>

<style scoped>

</style>
