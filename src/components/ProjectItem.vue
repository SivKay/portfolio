<script setup>
const props = defineProps({
  project: Object,
});
</script>

<template>
  <div class="project-item">
    <img class="project-img" :src="project.image" :alt="project.name" />
    <div class="overlay"></div>
    <div class="container">
      <h1>{{ project.name }}</h1>
      <div class="d-flex justify-center align-center ga-4">
        <div v-for="tech in project.techonologies" :key="tech.name">
          <v-card
            color="rgba(0, 0, 0, 0.1)"
            class="d-flex justify-center align-center pa-2"
            elevation="8"
            border="opacity-50 md"
            :style="{ borderColor: '#696969 !important' }"
          >
            <img
              class="tech-img"
              :src="tech.path"
              :alt="tech.name"
              width="56"
              height="56"
            />
          </v-card>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.project-item {
  position: relative;
  width: 100%;
  height: 300px;
  border-radius: 1rem;
  overflow: hidden;
}

.overlay {
  opacity: 0;
  position: absolute;
  inset: 0;
  transition: 0.5s ease;
  background-color: rgba(255, 255, 255, 0.1);
  z-index: -1;
  opacity: 0.9;
}

.container {
  position: absolute;
  inset: 0;
  transition: 0.5s ease;
  z-index: 1;
  opacity: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 1.5rem;
  gap: 1rem;
}

.project-item .project-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  backface-visibility: hidden;
}

.project-item:hover .project-img {
  opacity: 0.3;
}

.project-item:hover .container {
  opacity: 1;
}

@media (max-width: 480px) {
  .tech-img {
    width: 42px;
    height: 42px;
  }
}
</style>
