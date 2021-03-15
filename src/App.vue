<template>
  <TheTitle msg="Github Profile" />
  <div class="flex justify-around">
    <GithubUserCard
      v-for="(username, index) in usernames"
      :username="username"
      :key="index"
    />
  </div>
</template>

<script setup>
import TheTitle from "./components/TheTitle.vue";
import GithubUserCard from "./components/GithubUserCard.vue";

const usernames = ["hootlex", "rahaug", "sdras", "akryum"];
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
