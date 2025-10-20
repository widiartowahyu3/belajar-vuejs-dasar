<template>
  <Container>
    <template #header="attributes">
      <h1>Button App {{ attributes.counter }}</h1>
    </template>
    <template v-slot:default="attributes">
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Inventore
        natus, ratione error placeat cupiditate esse aliquid praesentium tempora
        cum pariatur fuga eum distinctio rerum quod accusamus ipsa magni
        provident eos amet, eaque odit sapiente! Soluta aspernatur ducimus
        deleniti laudantium. Excepturi ad in placeat, similique dolorem ipsam
        maxime neque minima vero porro id fugiat commodi est, deleniti quam vel
        corporis doloribus molestias eveniet quibusdam, praesentium quos!
        Molestias dicta mollitia sit asperiores ratione harum esse libero
        inventore, quos excepturi nihil adipisci dolorem natus facilis eaque
        repellat quam, incidunt rerum labore sequi exercitationem? Ut incidunt
        porro facere corporis totam quaerat vero consectetur provident?
      </p>
      <MyButton
        class="button"
        @click="clickHandler"
        :name="attributes.counter"
      />
    </template>
    <template #footer>
      <p>Copyright @wahyu widiarto</p>
    </template>
  </Container>
</template>
<script setup>
import Container from "./Container.vue";
import MyButton from "./MyButton.vue";

function clickHandler() {
  alert("you click me");
}
</script>
<style scoped>
.button {
  display: inline-block;
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  font-size: 16px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  text-align: center;
  transition: background-color 0.3s ease, transform 0.2s ease;
}
</style>
