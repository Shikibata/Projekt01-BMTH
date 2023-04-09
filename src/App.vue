<script setup>
import { RouterLink, RouterView } from "vue-router";
import Navbar from "./components/TheNav.vue";
</script>

<template>
  <Navbar />
  <RouterView />
</template>

<style>
@font-face {
  font-family: "Shirens";
  src: local("Shirens"),
  url("assets/SHIRENS.ttf") format("truetype");
}
</style>
