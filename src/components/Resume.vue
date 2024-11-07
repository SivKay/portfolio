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
    date: "Apr/2014-Oct/2015",
    title: "Frontend Web Developer Internship",
    subTitle: "RRPS Pharmas",
    description:
      "Work in a group of four developers to produce an e-commerce website, transform UI into website interfaces and integrate with firebase",
  },
  {
    id: 4,
    date: "Feb/2023-Present",
    title: "Frontend Engineer",
    subTitle: "IG Tech Group",
    description:
      "Work with UI designer to produce a responsive website, Collaborate closely with backend developers and the quality assurance team as well as clients to ensure to produce the quality work, implement code standard and reusable components and able to manage multiple tasks",
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
