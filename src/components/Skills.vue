<script setup>
import { ref } from "vue";
import SkillItem from "./SkillItem.vue";
import htmlIcon from "../assets/html.svg";
import cssIcon from "../assets/css.svg";
import jsIcon from "../assets/js.svg";
import angularIcon from "../assets/angular.svg";
import primengIcon from "../assets/primeng.svg";
import primeFlexIcon from "../assets/primeflex.svg";
import vueIcon from "../assets/vue.svg";
import vuetifyIcon from "../assets/vuetify.png";
import vuexIcon from "../assets/vuex.png";
import tailwindIcon from "../assets/tailwind.svg";
import reactIcon from "../assets/react.svg";

const skills = ref([
  {
    name: "HTML",
    path: htmlIcon,
  },
  {
    name: "CSS",
    path: cssIcon,
  },
  {
    name: "Javascript",
    path: jsIcon,
  },
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
  {
    name: "Vue",
    path: vueIcon,
  },
  {
    name: "Vuetify",
    path: vuetifyIcon,
  },
  {
    name: "Vuex",
    path: vuexIcon,
  },
  {
    name: "Tailwind",
    path: tailwindIcon,
  },
  {
    name: "React",
    path: reactIcon,
  },
]);
</script>

<template>
  <section id="skills">
    <div class="header position-relative text-center mb-8">
      <h1 class="title-shadow">Skills</h1>
      <h2>Skills</h2>
    </div>

    <div class="skill-list">
      <SkillItem
        v-for="skill in skills"
        :key="skill.name"
        :skill="skill"
      ></SkillItem>
    </div>
  </section>
</template>

<style scoped>
.skill-list {
  display: grid;
  grid-template-columns: repeat(6, minmax(0, 1fr));
  gap: 2.5rem;
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

@media (max-width: 1024px) {
  .skill-list {
    gap: 1.75rem;
  }
}

@media (max-width: 768px) {
  .header h2 {
    font-size: 2.375rem;
  }

  .skill-list {
    grid-template-columns: repeat(5, minmax(0, 1fr));
  }
}

@media (max-width: 480px) {
  .skill-list {
    grid-template-columns: repeat(4, minmax(0, 1fr));
    gap: 1rem;
  }
}
</style>
