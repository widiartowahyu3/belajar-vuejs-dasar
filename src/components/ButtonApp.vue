<template>
  <MyButton class="button" @click="clickHandler" />
</template>
<script setup>
import MyButton from "./MyButton.vue";

function clickHandler() {
  alert("you click me");
}
</script>
<style scoped>
.button {
  background-color: aqua;
  color: white;
}
</style>
