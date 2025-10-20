<template>
  <!-- <h1>{{ title }}</h1> -->
  <div v-if="slots.header">
    <slot name="header" :counter="counter">
      <h1>default header</h1>
    </slot>
  </div>
  <div v-if="slots.default">
    <slot name="default" :counter="counter">
      <p>Anda belum mengisi konten nya</p>
    </slot>
  </div>
  <div v-if="slots.footer">
    <slot name="footer" :counter="counter">
      <p>default footer</p>
    </slot>
  </div>
  <div>
    <button @click="counter++">Increment Counter</button>
  </div>
</template>
<script setup>
import { ref, useSlots } from "vue";

const slots = useSlots();
const counter = ref(0);
</script>
<style scoped></style>
