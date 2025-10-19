<template>
  <h1>Preview</h1>

  <div>
    <p>Name: {{ name }}</p>
    <p>email: {{ email }}</p>
    <p>age: {{ age }}</p>
    <p>type: {{ type }}</p>
    <p>complain: {{ complain }}</p>
    <p>message: {{ message }}</p>
  </div>
</template>

<script setup>
const [name, modifiers] = defineModel("name", {
  type: String,
  get: (value) => {
    if (modifiers.uppercase) {
      return value.toUpperCase();
    } else {
      return value;
    }
  },
});
const email = defineModel("email", {
  type: String,
});
const age = defineModel("age", {
  type: Number,
});
const type = defineModel("type", {
  type: String,
});
const complain = defineModel("complain", {
  type: Boolean,
});
const message = defineModel("message", {
  type: String,
});
</script>
<style scoped></style>
