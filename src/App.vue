<script setup>
import NavBar from "./components/NavBar.vue";
import Home from "./components/Home.vue";
import About from "./components/About.vue";
import Resume from "./components/Resume.vue";
import Skills from "./components/Skills.vue";
</script>

<template>
  <NavBar></NavBar>

  <Home />
  <About />
  <Resume />
  <Skills />
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
