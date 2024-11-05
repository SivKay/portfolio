<script setup>
import { ref } from "vue";
import { onMounted, onBeforeMount } from "vue";

const sections = ref([
  { id: "home", name: "Home" },
  { id: "about", name: "About" },
  { id: "resume", name: "Resume" },
  { id: "skills", name: "Skills" },
  { id: "projects", name: "Projects" },
  { id: "contact", name: "Contact" },
]);

const activeSection = ref("");

onMounted(() => {
  window.addEventListener("scroll", onScroll);
});

onBeforeMount(() => {
  window.addEventListener("scroll", onScroll);
});

function setActiveSection(id) {
  activeSection.value = id;
}

function onScroll() {
  // Detect the currently active section based on scroll position
  sections.value.forEach((section) => {
    const element = document.getElementById(section.id);
    const rect = element.getBoundingClientRect();
    if (rect.top <= 80 && rect.bottom >= 60) {
      activeSection.value = section.id;
    }
  });
}
</script>

<template>
  <nav>
    <a href="#home" class="navbar-logo">Kay</a>
    <ul>
      <li v-for="section in sections" class="nav-item" :key="section.id">
        <a
          :href="'#' + section.id"
          class="nav-link"
          :class="{ active: activeSection === section.id }"
          @click="setActiveSection(section.id)"
          ><span>{{ section.name }}</span></a
        >
      </li>
    </ul>
  </nav>
</template>

<style scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: sticky;
  top: 0;
  left: 0;
  right: 0;
  z-index: 10;
  background-color: var(--vt-c-black);
}

.navbar-logo {
  text-transform: uppercase;
  font-size: 1.5rem;
  font-weight: 900;
  text-decoration: none;
  color: var(--vt-c-white);
  padding: 1rem 0rem;
  margin-right: 1rem;
}

nav ul {
  display: flex;
  align-items: center;
}

.nav-item {
  list-style-type: none;
  padding: 0.75rem 1.25rem;
  cursor: pointer;
}

.nav-item:hover .nav-link span::before,
.nav-link.active span::before {
  visibility: visible;
  transform: scaleX(1);
}

.nav-link {
  text-decoration: none;
  color: var(--vt-c-white);
}

.nav-link.active {
  color: var(--vt-c-yellow) !important;
}

.nav-link span {
  position: relative;
  font-weight: 500;
  padding-bottom: 2px;
}

.nav-link span::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 2px;
  bottom: 0;
  left: 0;
  background: #ffbd39;
  visibility: visible;
  transform: scaleX(0);
  transition: all 0.3s ease-in-out 0s;
}
</style>
