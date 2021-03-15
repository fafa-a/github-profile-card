<template>
  <div class="w-full max-w-sm overflow-hidden bg-white border rounded shadow">
    <div class="relative">
      <img :src="user.avatar_url" />
    </div>
    <div class="p-3">
      <h3 class="mr-10 text-lg truncate-2nd">
        <a
          class="hover:text-blue-500"
          :href="`https://github.com/${props.username}`"
          >{{ user.name }}</a
        >
      </h3>
      <div class="flex items-start justify-between py-1">
        <p class="text-sm text-gray-500">Joined in {{ user.created_at }}</p>
      </div>
      <p class="text-sm text-gray-500">
        {{ user.bio }}
      </p>
      <p class="py-1 text-xs text-gray-500">
        <a :href="`https://github.com/${props.username}?tab=followers`">
          {{ user.followers }} Friends</a
        >
      </p>
    </div>
  </div>
</template>

<script setup>
import axios from "axios";
import { defineProps, ref } from "vue";
const props = defineProps({
  username: {
    type: String,
    required: true,
  },
});
const user = ref({});

axios.get(`https://api.github.com/users/${props.username}`).then((res) => {
  user.value = res.data;
});
</script>

<style></style>
