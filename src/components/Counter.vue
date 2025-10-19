<template>
  <h1 id="count">Counter {{ props.name }} = {{ counter.count }}</h1>
  <button v-on:click="increment">increment</button>
</template>
<script setup>
import { nextTick, ref } from "vue";

const props = defineProps(["name", "initialCount"]);

let counter = ref({
  count: Number(props.initialCount),
  nama: "wahyu",
});
async function increment() {
  console.log(`Increment counter: ${counter.value.count}`);
  counter.value = {
    nama: counter.value.nama,
    count: counter.value.count + 1,
  };

  await nextTick();
  counter.value.count++;
  await nextTick();
  counter.value.count++;
  await nextTick();
  counter.value.count++;
  counter.value.count++;
  counter.value.count++;
  counter.value.count++;

  await nextTick();

  console.log("increment come after next tick");
}
</script>
<style scoped></style>
