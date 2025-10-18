<template>
  <div>
    <form action="">
      <button v-on:click="counter++">Increment {{ counter }}</button><br />
      <label for="">First Name</label>
      <input
        @input="changeFirstName"
        placeholder="First Name"
        type="text"
        id="firstName"
      />
      <br />
      <label for="">Last Name</label>
      <input
        @input="changeLastName"
        placeholder="Last Name"
        type="text"
        id="lastName"
      />
      <br />
      <button v-on:click.prevent="sayHello">say hello</button>
      <!--prevent ini adalah salah satu dari modifier yang ada du vue yang memudahkan dalam scripting, ini mencegah untuk me reload halaman karena di bungkus dalam bentuk form jika di klik tombol say hello nya-->
    </form>
  </div>
  <h1>Hello {{ fullName }}</h1>
</template>
<script setup>
import { computed, reactive, ref } from "vue";

let person = reactive({
  firstName: "",
  lastName: "",
});
// reactive ini tipe datanya hanyalah object dan tidak bisa untuk tipe data primitive yaitu string, number, boolean

function sayHello(event) {
  person.firstName = document.getElementById("firstName").value;
  person.lastName = document.getElementById("lastName").value;
}

const fullName = computed((oldName) => {
  console.log(`Change Old Name ${oldName}`); // oldname ini adalah nama sebelum di ubah di inputan first name ataupun lastname
  return `${person.firstName} ${person.lastName}`;
});

const counter = ref(0);

function changeFirstName(event) {
  person.firstName = event.target.value;
}

function changeLastName(event) {
  person.lastName = event.target.value;
}
</script>
<style scoped></style>
