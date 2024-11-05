<script setup>
const props = defineProps({
  skill: Object,
});
</script>

<template>
  <v-tooltip :text="skill.name" location="top" v-slot:activator="{ props }">
    <div class="skill-container">
      <img :src="skill.path" :alt="skill.name" v-bind="props" />
    </div>
  </v-tooltip>
</template>

<style scoped>
.skill-container {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 5px;
  aspect-ratio: 1 / 1;
  padding: 2rem;
}

.skill-container img {
  width: 100%;
  height: 100%;
}

@media (max-width: 1280px) {
  .skill-container {
    padding: 1.5rem;
  }
}

@media (max-width: 1024px) {
  .skill-container {
    padding: 1rem;
  }
}
</style>
