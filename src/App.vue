<script setup>
import { ref, onErrorCaptured } from "vue";
import Result from "./components/Result.vue";

const error = ref(null);

onErrorCaptured(() => {
    error.value = "Ohh! Something went wrong!";
});
</script>

<template>
    <div v-if="error">{{ error }}</div>
    <Suspense v-else>
        <template #default>
            <Result />
        </template>
        <template #fallback>
            <h1>Loading...</h1>
        </template>
    </Suspense>
</template>

<style>
html,
body {
    font-size: 100%;
    overflow-x: hidden;
    align-content: center;
    background-color: #efe8df;
    color: #173353;
    display: grid;
    justify-content: center;
    min-height: 100vh;
}

*,
*::before,
*::after {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    line-height: 1.3;
}

a {
    text-decoration: none;
}
</style>
