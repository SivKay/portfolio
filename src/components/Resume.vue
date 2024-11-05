<script setup>
import { ref } from "vue";
import ResumeItem from "./ResumeItem.vue";

const items = ref([
  {
    id: 1,
    date: "2017-2021",
    title: "Bachelor Degree of Computer Science",
    subTitle: "Royal University of Phnom Penh",
    description: "",
  },
  {
    id: 2,
    date: "2018-2022",
    title: "Bachelor Degree of Department of English",
    subTitle: "Institute of Foreign Languages",
    description: "",
  },
  {
    id: 3,
    date: "2014-2015",
    title: "Frontend Web Developer Internship",
    subTitle: "RRPS Pharmas",
    description: "testing",
  },
  {
    id: 4,
    date: "Feb/2022-Present",
    title: "Frontend Engineer",
    subTitle: "Royal University of Phnom Penh",
    description: "Testing",
  },
]);
</script>

<template>
  <section id="resume">
    <div class="header position-relative text-center mb-8">
      <h1 class="title-shadow">Resume</h1>
      <h2>Resume</h2>
    </div>

    <div class="resume-list">
      <ResumeItem
        v-for="item in items"
        :key="item.id"
        :item="item"
      ></ResumeItem>
    </div>
  </section>
</template>

<style scoped>
section#resume {
  padding-top: 7rem;
  height: auto !important;
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

.resume-list {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 30px;
}

@media (max-width: 768px) {
  .header h2 {
    font-size: 2.375rem;
  }

  .resume-list {
    grid-template-columns: auto;
  }
}
</style>
