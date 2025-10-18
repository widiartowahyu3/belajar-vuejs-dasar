<template>
    <h1 v-bind="data">{{ hello.toUpperCase() }}</h1> <!-- tanda kurung kurawal dua atau biasa disebut dengan mustache vue ini digunakan untuk memanggil nama variable atau data di js nya ke html -->
    <h2>{{ 300 * 400 }}</h2>
    <div :class="data.class" v-html="hello"></div> <!--  berguna untuk memanggil raw html seperti tag <h1></h1> -->
    <!-- catatan ku
     composition api pakai script setup. atribute setup digunakan sebagai penanda  untuk vue melakukan proses trnasformasi sehingga membolehkan kita menggunakan composition api. biasanya menggunakan import tunction
     -->
     <h1>{{ helloFunction() }}</h1>
     <button :disabled="buttonDisabled">this is button</button>
</template>
<script setup>
console.info("hello vue");
const hello = "<h1> HELLO VUE </h1>";
const buttonDisabled = false;
const data ={
    id : "hello",
    class: "hello"
}

function helloFunction() {
    return "hello world";
}
</script>

<style scoped>
.hello{
    color: green;
}
</style>

