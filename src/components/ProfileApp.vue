<template>
  <input type="text" v-model="profile.name" placeholder="Nama" />
  <Profile />
  <ProfileAddress />
</template>
<script setup>
import { provide, reactive } from "vue";
import Profile from "./Profile.vue";
import ProfileAddress from "./ProfileAddress.vue";

const profile = reactive({
  name: "Wahyu",
  email: "widi@widi.com",
});

provide("profile", profile);
</script>
<style scoped></style>
