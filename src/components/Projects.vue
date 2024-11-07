<script setup>
import { ref } from "vue";

import angularIcon from "../assets/angular.svg";
import primengIcon from "../assets/primeng.svg";
import primeFlexIcon from "../assets/primeflex.svg";
import vueIcon from "../assets/vue.svg";
import vuexIcon from "../assets/vuex.png";
import tailwindIcon from "../assets/tailwind.svg";

import ProjectItem from "./ProjectItem.vue";
import project1 from "../assets/project1.jpg";
import project2 from "../assets/project2.jpg";
import project3 from "../assets/project3.jpg";

const projects = ref([
  {
    name: "Insurance Core System",
    image: project1,
    techonologies: [
      {
        name: "Vue",
        path: vueIcon,
      },
      {
        name: "Vuex",
        path: vuexIcon,
      },
      {
        name: "Tailwind",
        path: tailwindIcon,
      },
    ],
  },
  {
    name: "Customer Portal",
    image: project2,
    techonologies: [
      {
        name: "Angular",
        path: angularIcon,
      },
      {
        name: "PrimeNG",
        path: primengIcon,
      },
      {
        name: "PrimeFlex",
        path: primeFlexIcon,
      },
    ],
  },
  {
    name: "Admin Portal",
    image: project3,
    techonologies: [
      {
        name: "Angular",
        path: angularIcon,
      },
      {
        name: "PrimeNG",
        path: primengIcon,
      },
      {
        name: "PrimeFlex",
        path: primeFlexIcon,
      },
    ],
  },
]);
</script>

<template>
  <section id="projects">
    <div class="header position-relative text-center mb-8">
      <h1 class="title-shadow">Projects</h1>
      <h2>Projects</h2>
    </div>

    <div class="project-list">
      <ProjectItem
        v-for="project in projects"
        :key="project.name"
        :project="project"
      ></ProjectItem>
    </div>
  </section>
</template>

<style scoped>
.project-list {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 2rem;
}

.header h2 {
  font-size: 3.125rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
}

.title-shadow {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  font-size: min(7vw, 6rem);
  color: rgba(255, 255, 255, 0.1);
  z-index: -1;
  font-weight: 900;
}

@media (max-width: 768px) {
  .project-list {
    grid-template-columns: auto;
  }
}
</style>
