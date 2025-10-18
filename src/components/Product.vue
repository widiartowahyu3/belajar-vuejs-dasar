<template>
  <label for="productId">
    Product Id:
    <select v-model="productId">
      <!-- <option value=""></option> -->
      <option value="product1">Product 1</option>
      <option value="product2">Product 2</option>
      <option value="product3">Product 3</option>
    </select>
  </label>
  <div v-if="product">
    <h1>Product</h1>
    <p>Id: {{ product.id }}</p>
    <p>Name: {{ product.name }}</p>
    <p>Price: {{ product.price }}</p>
  </div>
</template>
<script setup>
import { onWatcherCleanup, ref, watch, watchEffect } from "vue";

// const productId = ref(0);
const productId = ref("product1");
const product = ref(null);

// watch(productId, async (newVal, oldVal) => {
// console.log(`call with watchers`);
//   if (newVal) {
//     const response = await fetch(`/${newVal}.json`);
//     console.log(response);
//     product.value = await response.json();
//   } else {
//     product.value = null;
//   }
// });

// watch(
//   productId,
//   async (newVal, oldVal) => {
//     console.log(`call with watchers`);
//     const response = await fetch(`/${newVal}.json`);
//     product.value = await response.json();
//   },
//   {
//     immediate: true,
//     once: true,
//   }
// );

// watchEffect(async (newVal, oldVal) => {
//   console.log(`call with watchers`);
//   const response = await fetch(`/${productId.value}.json`);
//   product.value = await response.json();
// });

watchEffect(async (newVal, oldVal) => {
  onWatcherCleanup(() => {
    console.log("cleanup");
  });
  //cleanup dilakukan ketika ingin melakukan callback watch sleanjutnya. jadi kalau pengen manggil web socket di bawah sebagai callback maka lebih baik di cleanup terlebih dahulu dengan men disconnect nya

  console.log(`call with watchers`);
  const response = await fetch(`/${productId.value}.json`);
  product.value = await response.json();
});
</script>
<style scoped></style>
