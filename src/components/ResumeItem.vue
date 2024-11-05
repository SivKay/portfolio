<script setup>
const props = defineProps({
  item: Object,
});
</script>

<template>
  <div class="resume-item">
    <span class="date font-weight-black">{{ item.date }}</span>
    <h2 class="title mb-2">{{ item.title }}</h2>
    <span class="sub-title">{{ item.subTitle }}</span>
    <p v-if="item.description" class="description mt-6 mb-4">
      {{ item.description }}
    </p>
  </div>
</template>

<style scoped>
.resume-item {
  padding: 1.875rem;
  border-radius: 5px;
  background-color: rgba(255, 255, 255, 0.1);
}

.resume-item .date {
  font-size: 1.625rem;
  color: var(--vt-c-yellow);
}

.resume-item .title {
  font-size: 1.625rem;
}

.resume-item .sub-title {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--vt-c-gray);
}

.resume-item .description {
  color: var(--vt-c-gray);
}
</style>
