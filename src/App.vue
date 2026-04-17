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
  padding: 20px;
}

/* MAIN CONTENT */
.main-content {
  display: flex;
  flex-direction: column;
  gap: 60px;
  padding: 30px;
}

/* SECTION STYLE */
.main-content > * {
  background: rgba(255, 255, 255, 0.03);
  padding: 25px;
  border-radius: 15px;
  backdrop-filter: blur(10px);
  transition: 0.3s;
}

.main-content > *:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0,0,0,0.4);
}

/* NAVBAR */
nav {
  display: flex;
  justify-content: center;
  gap: 25px;
  padding: 15px;
  background: rgba(255,255,255,0.05);
  border-radius: 12px;
  margin-bottom: 30px;
  backdrop-filter: blur(10px);
}

nav a {
  text-decoration: none;
  color: #00d4ff;
  font-weight: 600;
  padding: 8px 16px;
  border-radius: 6px;
  transition: 0.3s;
}

nav a:hover {
  background: #00d4ff;
  color: #000;
}
</style>