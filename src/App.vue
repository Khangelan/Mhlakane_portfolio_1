<script setup>
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import About from './components/About.vue'
import Experience from './components/Experience.vue'
import Projects from './components/Projects.vue'
import Certificates from './components/Certificates.vue'
import Contact from './components/Contact.vue'
</script>

<template>
  <div class="app-container">
    <Navbar />

    <main class="main-content">
      <Home />
      <About />
      <Experience />
      <Projects />
      <Certificates />
      <Contact />
    </main>
  </div>
</template>

<style>
/* RESET */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  min-height: 100%;
  width: 100%;
  overflow-x: hidden;
}

/* BODY */
body {
  font-family: 'Arial', sans-serif;
  background: linear-gradient(135deg, #0f172a, #1e293b);
  color: #e2e8f0;
}

/* APP CONTAINER */
.app-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px 16px;
}

/* MAIN CONTENT */
.main-content {
  display: flex;
  flex-direction: column;
  gap: 50px;
  padding: 20px 0;
}

/* SECTION STYLE */
.main-content > * {
  background: rgba(255, 255, 255, 0.03);
  padding: 25px;
  border-radius: 15px;
  backdrop-filter: blur(10px);
  transition: 0.3s;
  width: min(100%, 100%);
}

.main-content > *:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
}

/* NAVBAR */
nav {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
  padding: 14px 16px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 12px;
  margin-bottom: 30px;
  backdrop-filter: blur(10px);
  flex-wrap: wrap;
}

nav a {
  text-decoration: none;
  color: #00d4ff;
  font-weight: 600;
  padding: 8px 14px;
  border-radius: 6px;
  transition: 0.3s;
}

nav a:hover {
  background: #00d4ff;
  color: #000;
}

@media (max-width: 900px) {
  .app-container {
    padding: 16px;
  }

  .main-content {
    gap: 35px;
    padding: 16px 0;
  }

  .main-content > * {
    padding: 20px;
  }
}

@media (max-width: 640px) {
  nav {
    padding: 12px 12px;
  }

  nav a {
    padding: 10px 14px;
    font-size: 0.95rem;
  }
}
</style>
