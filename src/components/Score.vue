<template>
  <h1>SCORE APP</h1>
  <div v-show="score > 50">
    <p>Score nya adalah {{ score }}</p>
  </div>
  <div v-if="score > 90">
    <h4>yay nilai sempurna {{ score }}</h4>
  </div>
  <div v-else-if="score > 70">
    <h4>yay nilai bagus {{ score }}</h4>
  </div>
  <div v-else>
    <h4>yay nilai jelek {{ score }}</h4>
  </div>
</template>
<script setup>
import { ref } from "vue";

const score = ref(30);
</script>
<style scoped></style>
