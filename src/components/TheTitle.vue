<template>
  <h1 class="my-5 text-4xl text-center">{{ text }}</h1>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  text: String,
});
</script>
