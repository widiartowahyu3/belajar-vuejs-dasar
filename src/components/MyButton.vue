<template>
  <button>My Button : {{ attributes.name }}</button>
</template>
<script setup>
import { useAttrs } from "vue";

// defineOptions({
//   inheritAttrs: false,
// });

const props = defineProps(["contoh"]);
console.info(props);

const attributes = useAttrs();
console.info(attributes);
</script>
<style scoped></style>
