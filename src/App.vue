<script setup>
import { ref, onMounted, watch } from 'vue'
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import About from './components/About.vue'
import Experience from './components/Experience.vue'
import Projects from './components/Projects.vue'
import Certificates from './components/Certificates.vue'
import Contact from './components/Contact.vue'

const isLightMode = ref(false)

const toggleTheme = () => {
  isLightMode.value = !isLightMode.value
  window.localStorage.setItem('theme', isLightMode.value ? 'light' : 'dark')
}

onMounted(() => {
  const storedTheme = window.localStorage.getItem('theme')
  if (storedTheme === 'light') {
    isLightMode.value = true
  } else if (storedTheme === 'dark') {
    isLightMode.value = false
  } else if (window.matchMedia('(prefers-color-scheme: light)').matches) {
    isLightMode.value = true
  }
  document.documentElement.classList.toggle('light-mode', isLightMode.value)
})

watch(isLightMode, (value) => {
  document.documentElement.classList.toggle('light-mode', value)
}, { immediate: true })
</script>

<template>
  <div class="app-container">
    <Navbar :is-light-mode="isLightMode" @toggle-theme="toggleTheme" />

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
:root {
  --bg-start: #0f172a;
  --bg-end: #1e293b;
  --page-text: #e2e8f0;
  --surface: rgba(255, 255, 255, 0.03);
  --surface-strong: rgba(255, 255, 255, 0.05);
  --surface-hover: rgba(255, 255, 255, 0.08);
  --nav-bg: rgba(255, 255, 255, 0.05);
  --link-color: #00d4ff;
  --link-hover-bg: #00d4ff;
  --link-hover-text: #000;
  --shadow: rgba(0, 0, 0, 0.4);
}

html.light-mode {
  --bg-start: #e0f2fe;
  --bg-end: #dbeafe;
  --page-text: #000;
  --surface: rgba(255, 255, 255, 0.85);
  --surface-strong: rgba(255, 255, 255, 0.95);
  --surface-hover: rgba(255, 255, 255, 0.95);
  --nav-bg: rgba(255, 255, 255, 0.95);
  --link-color: #0c4a6e;
  --link-hover-bg: #bae6fd;
  --link-hover-text: #000;
  --shadow: rgba(15, 23, 42, 0.12);
}

html.light-mode .home {
  background: linear-gradient(135deg, #dbeafe, #e0f2fe) !important;
  color: #000 !important;
}

html.light-mode .home .overlay {
  background: radial-gradient(circle, rgba(59, 130, 246, 0.22), transparent) !important;
}

html.light-mode .home .primary {
  background: #0c4a6e !important;
  color: #fff !important;
}

html.light-mode .home .secondary {
  background: transparent !important;
  border-color: #0c4a6e !important;
  color: #0c4a6e !important;
}

html.light-mode .about-section {
  color: #0f172a !important;
}

html.light-mode .highlight {
  color: #0c4a6e !important;
}

html.light-mode .tags span {
  background: rgba(14, 165, 233, 0.12) !important;
  color: #0c4a6e !important;
}

html.light-mode .download-btn {
  background: #0c4a6e !important;
  color: white !important;
}

html.light-mode .about-card .card {
  background: rgba(255, 255, 255, 0.9) !important;
  border-color: rgba(15, 23, 42, 0.08) !important;
  box-shadow: 0 20px 40px rgba(15, 23, 42, 0.08) !important;
}

html.light-mode .about-card .card-item {
  color: #000 !important;
}

html.light-mode .experience-section {
  background: linear-gradient(180deg, rgba(224, 242, 254, 0.95), rgba(219, 234, 254, 0.92)) !important;
}

html.light-mode .experience-header h2,
html.light-mode .experience-header p,
html.light-mode .role,
html.light-mode .duration,
html.light-mode .experience-card li {
  color: #000 !important;
}

html.light-mode .section-label {
  background: rgba(14, 165, 233, 0.18) !important;
  color: #0c4a6e !important;
}

html.light-mode .experience-card {
  background: rgba(255, 255, 255, 0.9) !important;
  border-color: rgba(15, 23, 42, 0.08) !important;
  box-shadow: 0 20px 50px rgba(15, 23, 42, 0.08) !important;
}

html.light-mode .certificate-card,
html.light-mode .contact-form,
html.light-mode .skill-card,
html.light-mode .card-inner,
html.light-mode .project-info {
  background: rgba(255, 255, 255, 0.92) !important;
}

html.light-mode .certificates-section {
  background: linear-gradient(180deg, rgba(235, 248, 255, 0.95), rgba(219, 234, 254, 0.9)) !important;
}

html.light-mode .certificate-card h3,
html.light-mode .certificate-card p,
html.light-mode .issuer,
html.light-mode .section-heading h2,
html.light-mode .section-heading p,
html.light-mode .project-description,
html.light-mode .type-label,
html.light-mode .status-signal {
  color: #000 !important;
}

html.light-mode .certificate-card .card-badge {
  background: #0c4a6e !important;
}

html.light-mode .certificate-card .card-tag {
  background: rgba(14, 165, 233, 0.12) !important;
  color: #0c4a6e !important;
}

html.light-mode .contact-section {
  color: #0f172a !important;
}

html.light-mode .contact-section h2,
html.light-mode .contact-section .subtitle,
html.light-mode .social-item,
html.light-mode .contact-form input,
html.light-mode .contact-form textarea,
html.light-mode .contact-form button {
  color: #000 !important;
}

html.light-mode .contact-form input,
html.light-mode .contact-form textarea {
  background: rgba(255, 255, 255, 0.95) !important;
  border-color: rgba(15, 23, 42, 0.1) !important;
}

html.light-mode .contact-form button {
  background: #0c4a6e !important;
  color: #ffffff !important;
}

html.light-mode .skills-section {
  background-color: #eff6ff !important;
}

html.light-mode .skills-section h2,
html.light-mode .skill-card h3,
html.light-mode .skill-card p {
  color: #000 !important;
}

html.light-mode .skill-card {
  background: white !important;
  box-shadow: 0 4px 16px rgba(15, 23, 42, 0.08) !important;
}

html.light-mode .skill-card i {
  color: #0c4a6e !important;
}

html.light-mode .synth-card {
  background: #f8fdff !important;
  border-color: #7dd3fc !important;
  box-shadow:
    0 0 20px rgba(14, 165, 233, 0.18),
    0 0 40px rgba(59, 130, 246, 0.08) !important;
}

html.light-mode .sunset-bg {
  background: linear-gradient(to bottom, #7dd3fc 0%, #38bdf8 28%, #bfdbfe 58%, transparent 100%) !important;
}

html.light-mode .grid-floor {
  background:
    linear-gradient(to bottom, transparent 0%, #f8fdff 100%) !important;
}

html.light-mode .card-inner {
  background: rgba(255, 255, 255, 0.95) !important;
}

html.light-mode .project-title,
html.light-mode .btn-text,
html.light-mode .btn-icon,
html.light-mode .project-description,
html.light-mode .platform,
html.light-mode .type-label,
html.light-mode .status-signal,
html.light-mode .stat-val {
  color: #0f172a !important;
}

html.light-mode .platform {
  background: rgba(14, 165, 233, 0.12) !important;
  border-color: rgba(14, 165, 233, 0.2) !important;
}

html.light-mode .synth-btn {
  background: rgba(14, 165, 233, 0.12) !important;
  border-color: #0c4a6e !important;
  color: #0f172a !important;
}

html.light-mode .btn-glow {
  opacity: 0.2 !important;
}

html.light-mode .synth-btn:hover {
  box-shadow:
    0 0 25px rgba(14, 165, 233, 0.4),
    0 0 50px rgba(59, 130, 246, 0.2) !important;
}

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
  background: linear-gradient(135deg, var(--bg-start), var(--bg-end));
  color: var(--page-text);
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
  background: var(--surface);
  padding: 25px;
  border-radius: 15px;
  backdrop-filter: blur(10px);
  transition: 0.3s;
  width: min(100%, 100%);
}

.main-content > *:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px var(--shadow);
}

/* NAVBAR */
nav {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
  padding: 14px 16px;
  background: var(--nav-bg);
  border-radius: 12px;
  margin-bottom: 30px;
  backdrop-filter: blur(10px);
  flex-wrap: wrap;
}

nav a {
  text-decoration: none;
  color: var(--link-color);
  font-weight: 600;
  padding: 8px 14px;
  border-radius: 6px;
  transition: 0.3s;
}

nav a:hover {
  background: var(--link-hover-bg);
  color: var(--link-hover-text);
}

.theme-toggle {
  background: var(--surface-strong);
  color: var(--page-text);
  border: 1px solid rgba(255, 255, 255, 0.25);
  padding: 8px 14px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
  transition: transform 0.3s, background-color 0.3s;
}

.theme-toggle:hover {
  transform: translateY(-1px);
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
