<script setup>
import NavBar from "./components/NavBar.vue";
</script>

<template>
  <NavBar></NavBar>

  <section id="home">Home</section>
  <section id="about">About</section>
  <section id="resume">Resume</section>
  <section id="skills">Skills</section>
  <section id="projects">Projects</section>
  <section id="contact">Contact</section>
</template>

<style scoped>
section {
  width: 100%;
  height: 300px;
  border: 1px solid red;
}
</style>
