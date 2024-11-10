<script setup>
import { onMounted, onUnmounted, ref } from "vue";

const isOpenMobileNav = ref(false);
const sections = ref([
  { id: "home", name: "Home" },
  { id: "about", name: "About" },
  { id: "resume", name: "Resume" },
  { id: "skills", name: "Skills" },
  { id: "projects", name: "Projects" },
  { id: "contact", name: "Contact" },
]);

const activeSection = ref("home");

onMounted(() => {
  window.addEventListener("scroll", onScroll);
  window.addEventListener("resize", onCloseNavbar);
});

onUnmounted(() => {
  window.removeEventListener("scroll", onScroll);
  window.removeEventListener("resize", onCloseNavbar);
});

function setActiveSection(id) {
  activeSection.value = id;
  isOpenMobileNav.value = false;
}

function onScroll() {
  sections.value.forEach((section) => {
    const element = document.getElementById(section.id);
    const rect = element.getBoundingClientRect();
    if (rect.top <= 80 && rect.bottom >= 60) {
      activeSection.value = section.id;
    }
  });
}

function onCloseNavbar() {
  if (window.innerWidth >= 768) {
    isOpenMobileNav.value = false;
  }
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

    <div class="mobile-nav">
      <v-btn
        color="var(--vt-c-white)"
        :icon="isOpenMobileNav ? 'mdi-close' : 'mdi-menu'"
        size="x-large"
        variant="text"
        @click="isOpenMobileNav = !isOpenMobileNav"
      ></v-btn>
      <v-expand-transition>
        <ul v-show="isOpenMobileNav" class="mobile-nav-items">
          <li
            v-for="section in sections"
            class="mobile-nav-item"
            :key="section.id"
          >
            <a
              :href="'#' + section.id"
              class="mobile-nav-link"
              :class="{ active: activeSection === section.id }"
              @click="setActiveSection(section.id)"
              ><span>{{ section.name }}</span></a
            >
          </li>
        </ul>
      </v-expand-transition>
    </div>
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
  transition: all ease;
}

.nav-item,
.mobile-nav-item {
  list-style-type: none;
  cursor: pointer;
}

.nav-item:hover .nav-link span::before,
.nav-link.active span::before,
.mobile-nav-item:hover .mobile-nav-link span::before,
.mobile-nav-link.active span::before {
  visibility: visible;
  transform: scaleX(1);
}

.nav-link,
.mobile-nav-link {
  display: block;
  text-decoration: none;
  padding: 0.75rem 1.25rem;
  color: var(--vt-c-white);
}

.mobile-nav-link.active,
.nav-link.active {
  color: var(--vt-c-yellow) !important;
}

.mobile-nav-link span,
.nav-link span {
  position: relative;
  font-weight: 500;
  padding-bottom: 2px;
}

.mobile-nav-link span::before,
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

.mobile-nav {
  display: none;
}

@media (max-width: 768px) {
  nav ul {
    display: none;
  }

  .mobile-nav-items {
    position: absolute;
    display: flex;
    flex-direction: column;
    top: 68px;
    left: 0px;
    width: 100%;
    height: calc(100vh - 68px);
    background: black;
  }

  .mobile-nav {
    display: block;
  }
}
</style>
