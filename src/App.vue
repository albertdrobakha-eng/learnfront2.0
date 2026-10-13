<script setup>
import { ref } from 'vue'

let message = ref('Hello Vue 3!')

function inputUpdate(event) {
    console.log(event);
    message = event.target.value;
}

</script>

<template>
    <button @click="message = 'Hello ta25b!'" class="button is-primary">Click me</button>
    <h1>{{ message }}</h1>
    <!-- <input type="text" class="input" v-model="message" @input="inputUpdate" /> -->
    <input type="text" class="input" v-model="message">
</template>

<style>

</style>