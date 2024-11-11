<script setup>
import TelegramIcon from "./Icons/TelegramIcon.vue";

function downloadCv() {
  const fileUrl = "/cv.pdf";
  const link = document.createElement("a");
  link.href = fileUrl;
  link.setAttribute("download", "yinh_sivkay_cv.pdf");
  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);
}
</script>

<template>
  <section id="about">
    <img src="../assets/profile.png" alt="profile" />
    <div class="about-container">
      <h1 class="title-shadow">About</h1>
      <h2>About Me</h2>
      <p class="about-description">
        Equipped with hands-on experience in creating responsive and visually
        appealing web interfaces. Proficient in Vue Js, Angular Js and React Js.
        Able to collaborate and adapt well as a part of productive team. A fast
        learner with a passion for staying updated with the latest technologies
        and trends in web development.
      </p>

      <div class="social-medias mb-4">
        <v-btn
          href="https://www.facebook.com/sivkay.yinh"
          variant="text"
          color="var(--vt-c-gray)"
          target="_blank"
          rel="noopener noreferrer"
          rounded="xl"
        >
          <v-icon icon="mdi-facebook"></v-icon>
        </v-btn>
        <v-btn
          icon="mdi-linkedin"
          href="https://www.linkedin.com/in/yinh-sivkay-7679141a5"
          variant="text"
          color="var(--vt-c-gray)"
          target="_blank"
          rel="noopener noreferrer"
          rounded="xl"
        >
          <v-icon icon="mdi-linkedin"></v-icon>
        </v-btn>
        <v-btn
          href="https://t.me/Sivkayy"
          variant="text"
          color="var(--vt-c-gray)"
          target="_blank"
          rel="noopener noreferrer"
          rounded="xl"
        >
          <TelegramIcon />
        </v-btn>
      </div>

      <v-btn
        rounded="xl"
        size="large"
        color="var(--vt-c-yellow)"
        @click="downloadCv"
        >DOWNLOAD CV</v-btn
      >
    </div>
  </section>
</template>

<style scoped>
section#about {
  display: flex;
  padding-top: 7rem;
  height: auto !important;
}

.v-icon {
  font-size: 2rem !important;
}

img {
  width: 40%;
}

.about-container {
  position: relative;
  flex: 1;
  padding: 0 1rem 3rem 3rem;
}

.title-shadow {
  position: absolute;
  top: -10px;
  left: 32px;
  font-size: min(7vw, 6rem);
  color: rgba(255, 255, 255, 0.1);
  z-index: -1;
  font-weight: 900;
}

.about-container h2 {
  font-size: 3.125rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
}

.about-description {
  color: var(--vt-c-gray);
  margin-bottom: 1rem;
}

.social-medias > * {
  width: 3rem !important;
  min-width: 3rem !important;
  height: 3rem !important;
}

.social-medias > *:hover {
  color: var(--vt-c-yellow) !important;
}

@media (max-width: 1024px) {
  .about-container {
    padding-left: 1rem;
  }

  .title-shadow {
    top: 0;
    left: 0;
  }
}

@media (max-width: 768px) {
  img {
    display: none;
  }

  .about-container h2 {
    font-size: 2.375rem;
  }
}
</style>
