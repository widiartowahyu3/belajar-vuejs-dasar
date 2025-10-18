<template>
  <h1>To Do List</h1>
  <!-- <ul>
    <li v-for="item in items">
      {{ item.text }}
    </li>
  </ul> -->
  <!-- <ul v-for="item in items">
    <li v-for="(value, key) in item">{{ key }}: {{ value }}</li>
  </ul> -->
  <!-- <ul v-for="item in items" :key="item.id">
    <li v-for="(value, key) in item">{{ key }}: {{ value }}</li>
  </ul> -->
  <template v-for="item in items">
    <ul :key="item.id" v-if="!item.done">
      <li v-for="(value, key) in item">{{ key }}: {{ value }}</li>
    </ul>
  </template>

  <div v-for="n in 10">
    <h1>heello {{ n }}</h1>
  </div>
</template>

<script setup>
const items = [
  {
    id: 1,
    text: "Learn Vue 3",
    done: true,
  },
  {
    id: 2,
    text: "Learn Vue Router 2",
    done: false,
  },
  {
    id: 3,
    text: "Learn Vue Pinia",
    done: false,
  },
  {
    id: 4,
    text: "Learn Vue Pinia 22",
    done: false,
  },
];
</script>

<style scoped></style>
