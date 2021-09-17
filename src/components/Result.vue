<script setup>
import { ref } from "vue";

const response = await fetch("http://openlibrary.org/search.json?q=the+lord+of+the+rings");
const data = await response.json();

const msg = ref(`It has been found: ${data.num_found} results!`);
</script>

<template>
    <h1>{{ msg }}</h1>
</template>

<style scoped></style>
