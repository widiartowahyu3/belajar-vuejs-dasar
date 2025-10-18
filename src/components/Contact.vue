<template>
  <h1>Contact Us</h1>
  <form action="">
    <div>
      <label for="name"
        >Name: <input type="text" id="name" v-model="contact.name"
      /></label>
    </div>
    <div>
      <label for="email"
        >Email: <input type="text" id="email" v-model="contact.email"
      /></label>
    </div>
    <div>
      <label for="age"
        >Age: <input type="text" id="age" v-model.number="contact.age"
      /></label>
    </div>
    <div>
      <label for="tyoe"
        >Type:
        <select name="" id="tyoe" v-model="contact.type">
          <option value="Regular">Regular</option>
          <option value="VIP">VIP</option>
        </select></label
      >
    </div>
    <div>
      <label for="complain"
        >Complain:
        <input type="checkbox" id="complain" v-model.number="contact.complain"
      /></label>
    </div>
    <div>
      <label for="message"
        >Message:
        <textarea
          name="message"
          id="message"
          v-model="contact.message"
        ></textarea>
      </label>
    </div>
  </form>

  <h1>Preview</h1>

  <div>
    <p>Name: {{ contact.name }}</p>
    <p>email: {{ contact.email }}</p>
    <p>age: {{ contact.age }}</p>
    <p>type: {{ contact.type }}</p>
    <p>complain: {{ contact.complain }}</p>
    <p>message: {{ contact.message }}</p>
  </div>
</template>
<script setup>
import { reactive } from "vue";

let contact = reactive({
  name: "",
  email: "",
  age: 0,
  type: "Regular",
  complain: false,
  message: "",
});

//directive model digunakan input binding dihubungkan dengan state contact nya daripada melakukan update saecara manual satu per satu
</script>
<style scoped></style>
