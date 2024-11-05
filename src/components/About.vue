<script setup>
function downloadCv() {
  const fileUrl = "../../public/test.pdf"; // Adjust the path based on your folder structure
  const link = document.createElement("a");
  link.href = fileUrl;
  link.setAttribute("download", "yinh_sivkay_cv.pdf"); // Specify the file name
  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);
}
</script>

<template>
  <section id="about">
    <img src="../assets/logo.svg" alt="profile" />
    <div class="about-container">
      <h1 class="title-shadow">About</h1>
      <h2>About Me</h2>
      <p class="about-description">
        As a front-end seveloper. I have successfully designed the user
        interface and worked closely with the backend team to integrate Apis.My
        role has involved resolving technical issues, optimizing application
        performance and exploring new technologies to ensure enhanced front-end
        development.I have consistently maintained coding standards for code
        reviews, team support and managing multiple tasks assigned by project
        managers.
      </p>

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

img {
  width: 40%;
  padding-inline: 1rem;
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
