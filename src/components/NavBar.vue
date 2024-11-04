<script setup></script>

<template>
  <nav>
    <img src="../assets/logo.svg" alt="logo" width="24" height="24" />
    <ul>
      <li class="nav-item">
        <a href="#home" class="nav-link"><span>Home</span></a>
      </li>
      <li class="nav-item">
        <a href="#about" class="nav-link"><span>About</span></a>
      </li>
      <li class="nav-item">
        <a href="#resume" class="nav-link"><span>Resume</span></a>
      </li>
      <li class="nav-item">
        <a href="#skills" class="nav-link"><span>Skills</span></a>
      </li>
      <li class="nav-item">
        <a href="#projects" class="nav-link"><span>Projects</span></a>
      </li>
      <li class="nav-item">
        <a href="#contact" class="nav-link"><span>Contact</span></a>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: sticky;
  top: 0;
  left: 0;
  right: 0;
  z-index: 10;
  background-color: var(--vt-c-black);
}

nav ul {
  display: flex;
  align-items: center;
}

.nav-item {
  list-style-type: none;
  padding: 0.75rem 1.25rem;
  cursor: pointer;
}

.nav-item:hover .nav-link span::before {
  visibility: visible;
  transform: scaleX(1);
}

.nav-link {
  text-decoration: none;
  color: var(--vt-c-white);
}

.nav-link:target {
  color: var(--vt-c-yellow) !important;
}

.nav-link span {
  position: relative;
  font-weight: 500;
  padding-bottom: 2px;
}

.nav-link span::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 2px;
  bottom: 0;
  left: 0;
  background: #ffbd39;
  visibility: visible;
  transform: scaleX(0);
  transition: all 0.3s ease-in-out 0s;
}
</style>
