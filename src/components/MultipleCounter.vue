<template>
  <Counter name="Wahyu" initial-count="10" />
  <Counter name="Widiarto" initial-count="20" />
  <!-- ini memanggil props yang ada di component counter yang dibuat dengan defineprops -->
  <CounterStateless
    name="wahyu"
    :counter="counter"
    :increment="1"
    @click="increment"
  />
  <CounterStateless
    name="widiarto"
    :counter="counter"
    :increment="2"
    @click="increment"
  />
</template>
<script setup>
import { ref } from "vue";
import Counter from "./Counter.vue";
import CounterStateless from "./CounterStateless.vue";

const counter = ref(0);

function increment(value) {
  counter.value += value;
}
</script>
<style scoped></style>
