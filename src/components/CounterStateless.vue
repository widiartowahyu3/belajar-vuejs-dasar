<template>
  <div>
    <h1>Counter {{ name }} : {{ counter }}</h1>
    <button @click="buttonClick">Increment {{ name }}</button>
  </div>
</template>
<script setup>
// const { counter, name } = defineProps(["counter", "name"]);
const { counter, name, increment } = defineProps({
  counter: Number,
  name: String,
  increment: Number,
});
const emits = defineEmits(["pencet"]);

function buttonClick() {
  emits("pencet", increment);
}
</script>
<style scoped></style>
