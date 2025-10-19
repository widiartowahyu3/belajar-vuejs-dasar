<template>
  <ContactForm v-model="contact" />
  <!-- <h1>Preview</h1>

  <div>
    <p>Name: {{ contact.name }}</p>
    <p>email: {{ contact.email }}</p>
    <p>age: {{ contact.age }}</p>
    <p>type: {{ contact.type }}</p>
    <p>complain: {{ contact.complain }}</p>
    <p>message: {{ contact.message }}</p>
  </div> -->

  <ContactList
    v-model:name.uppercase="contact.name"
    v-model:email="contact.email"
    v-model:age="contact.age"
    v-model:type="contact.type"
    v-model:complain="contact.complain"
    v-model:message="contact.message"
  />
  <!-- penjelasan v-model: name adallah v-model adalah  model nya dengan argument yang bernama name-->
</template>
<script setup>
import { reactive } from "vue";
import ContactForm from "./ContactForm.vue";
import ContactList from "./ContactList.vue";

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
