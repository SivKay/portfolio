<script setup></script>

<template>
  <section id="home">
    <div class="introduction">
      <p>Hello!</p>
      <h1>I'm <span>Yinh Sivkay</span></h1>
      <h2>Frontend Web Developer</h2>
    </div>
    <div class="profile"></div>
  </section>
</template>

<style scoped>
section {
  position: relative;
  height: calc(100vh - 76px) !important;
  padding-top: 0 !important;
}

section .profile {
  width: 65%;
  height: 100%;
  background-image: url("../assets/profile.png");
  background-position: center center;
  background-repeat: no-repeat;
  background-size: cover;
  margin-left: auto;
}

.introduction {
  position: absolute;
  top: 50%;
  left: 0;
  transform: translateY(-50%);
  max-width: 50%;
}

.introduction p {
  color: var(--vt-c-yellow);
  font-weight: 600;
  font-size: 0.875rem;
  letter-spacing: 3px;
  text-transform: uppercase;
}

.introduction h1 {
  font-size: 3.75rem;
  line-height: 1.2;
  font-weight: 800;
  margin-top: 1rem;
  margin-bottom: 1.5rem;
}

.introduction h1 span {
  color: var(--vt-c-yellow);
  font-weight: 800;
}

.introduction h2 {
  font-size: 1.875rem;
}

@media (max-width: 1024px) {
  section .profile {
    width: 100%;
  }

  .introduction {
    width: 100%;
    max-width: 100%;
    text-align: center;
  }

  .introduction h1 {
    font-size: 3.125rem;
  }
}

@media (max-width: 768px) {
  .introduction h1 {
    font-size: 2.5rem;
  }
}
</style>
