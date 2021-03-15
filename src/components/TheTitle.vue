<template>
  <h1 class="my-5 text-4xl ml-">{{ msg }}</h1>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  msg: String,
});
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
