<script setup>
import NavBar from "./components/NavBar.vue";
import Home from "./components/Home.vue";
import About from "./components/About.vue";
import Resume from "./components/Resume.vue";
import Skills from "./components/Skills.vue";
import Projects from "./components/Projects.vue";
import Contact from "./components/Contact.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <NavBar></NavBar>

  <Home />
  <About />
  <Resume />
  <Skills />
  <Projects />
  <Contact />

  <Footer />
</template>

<style scoped>
section {
  padding-top: 7rem;
}
</style>
