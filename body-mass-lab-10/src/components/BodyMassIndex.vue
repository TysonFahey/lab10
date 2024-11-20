<script setup>
import { ref } from "vue";

const userHeight = ref(); // set userHeight to nothing so the user can enter theirs easily ( if you wanted a default for the initial page load before user enters anything you put the number inside of the () ex. ref(1); 1 will be displayed in the input field)
const userWeight = ref(); // set userWeight to nothing so the user can enter theirs easily

const emit = defineEmits(["user-entered-data"]); // Set up user-entered-data so we can use the emit to send it outside of this component

const userHasSubmittedData = () => {
  emit("user-entered-data", userHeight.value, userWeight.value);
}; // this function emits user-entered-data and sends userHeight.value, userWeight.value to be able to be recieved by App.vue
</script>

<template>
  <h2>Enter your height and weight</h2>

  <label>Height in meters</label>
  <input v-model="userHeight" /> <!-- connect the userHeight input using v-model -->

  <br />

  <label>Weight in kilograms</label><input v-model="userWeight" />
<!-- connect the userWeight input using v-model -->
  <br />

  <button v-on:click="userHasSubmittedData">Calculate!</button>
  <!-- set up the button so that it uses v-on:click. when the user clicks the button, userHasSubmittedData function is called.-->
</template>

<style scoped>
button {
  background-color: lightblue;
}
</style>
