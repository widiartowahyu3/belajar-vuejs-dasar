<template>
  <h1>Buat Note</h1>
  <div>
    <input
      ref="noteInput"
      v-model="note"
      placeholder="Tulis Note Disini..."
      type="text"
    />
    <button @click="addNote">Tambah Note</button>
  </div>
  <h1>Daftar Note</h1>
  <ul>
    <li v-for="note in notes" ref="notesList">{{ note }}</li>
  </ul>
</template>
<script setup>
import {
  onBeforeMount,
  onMounted,
  onUpdated,
  reactive,
  ref,
  useTemplateRef,
} from "vue";

const notes = reactive([]);
const note = ref("");
const noteInput = useTemplateRef("noteInput");
const notesList = useTemplateRef("notesList");

// function addNote() {
//   if (note.value !== "") {
//     notes.push(note.value);
//     note.value = "";
//     noteInput.value.focus();
//     console.log(notes);
//   } else {
//     alert("harap jangan kosong");
//   }
// }
function addNote() {
  if (note.value !== "") {
    notes.push(note.value);
    note.value = "";
    noteInput.value.focus();
    if (notesList.value) {
      notesList.value.forEach((li) => {
        console.log(li.textContent);
      });
    }
  } else {
    alert("harap jangan kosong");
  }
}

onBeforeMount(() => {
  console.info("onbeforemount");
});

onMounted(() => {
  console.info("onMounted");
});

onUpdated(() => {
  console.info("onMounted");
});
</script>
<style scoped></style>
