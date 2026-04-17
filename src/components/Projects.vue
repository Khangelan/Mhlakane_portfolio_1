<template>
  <section id="Projects" class="projects-section">
    <header class="section-heading">
      <span class="section-label">Portfolio</span>
      <h2>Featured Projects</h2>
      <p>Four real projects built with modern web technologies, each showing the core tech and a live view link.</p>
    </header>

    <div class="project-grid">
      <article
        v-for="(project, index) in projects"
        :key="project.title"
        class="project-card synth-card"
        :class="{ 'is-hovered': hoveredIndex === index }"
      >
        <div class="sunset-bg"></div>
        <div class="grid-floor"></div>
        <div class="scanlines"></div>

        <div class="card-inner">
          <div
            class="image-wrapper"
            @mouseenter="hoveredIndex = index"
            @mouseleave="hoveredIndex = null"
          >
            <div class="retro-border">
              <div class="border-segment top"></div>
              <div class="border-segment right"></div>
              <div class="border-segment bottom"></div>
              <div class="border-segment left"></div>
            </div>

            <div class="image-container">
              <img :src="project.imageUrl" :alt="project.title" class="project-image" loading="lazy" />
              <div class="crt-overlay"></div>
              <div class="chromatic-aberration" v-if="hoveredIndex === index"></div>
            </div>

            <div class="image-overlay">
              <div class="overlay-content">
                <div class="game-stats">
                  <div class="stat-box">
                    <span class="stat-icon">💻</span>
                    <span class="stat-val">{{ project.tech }}</span>
                  </div>
                  <div class="stat-box">
                    <span class="stat-icon">🌐</span>
                    <span class="stat-val">{{ project.status }}</span>
                  </div>
                </div>
                <div class="play-button">
                  <div class="play-icon">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                      <path d="M8 5v14l11-7z" />
                    </svg>
                  </div>
                  <span class="play-text">View project</span>
                </div>
              </div>
            </div>

            <div class="floating-particles">
              <div class="particle" v-for="n in 6" :key="n" :style="{'--i': n}"></div>
            </div>
          </div>

          <div class="project-info">
            <div class="glitch-title" :class="{ glitching: hoveredIndex === index }">
              <h3 class="project-title">{{ project.title }}</h3>
              <span class="glitch-shadow" aria-hidden="true">{{ project.title }}</span>
              <span class="glitch-shadow-2" aria-hidden="true">{{ project.title }}</span>
            </div>

            <p class="project-description">{{ project.description }}</p>

            <div class="platform-tags">
              <span class="platform" v-for="platform in project.platforms" :key="platform">{{ platform }}</span>
            </div>

            <div class="card-footer">
              <a :href="project.projectUrl" class="view-project-btn synth-btn" target="_blank" rel="noreferrer">
                <span class="btn-glow"></span>
                <span class="btn-text">Open</span>
              </a>
              <div class="price-tag">
                <span class="original">{{ project.tech }}</span>
                <span class="sale">{{ project.status }}</span>
              </div>
            </div>
          </div>
        </div>
      </article>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const hoveredIndex = ref(null)

const projects = [
  {
    title: 'Hr-Management App',
    description: 'A sleek, responsive front-end application built with Vue.js that provides an intuitive interface for managing employee information, attendance, leave requests, and organizational data. Designed to be user-friendly and visually appealing, it serves as the interactive layer of an HR system, enabling HR teams and employees to access and update information seamlessly. The app features modern UI components, smooth animations, and clean layouts to enhance user experience.',
    imageUrl: 'https://images.unsplash.com/photo-1522071820081-009f0129c71c?w=900&q=80',
    projectUrl: 'https://github.com/Khangelan/CORE-PROJECT-1.git',
    platforms: ['Vue 3', 'Vite', 'CSS'],
    tech: 'Web App',
    status: 'Live',
  },
  {
    title: 'E-Commerce UI App',
    description: 'A complete online shopping platform developed with a modern front-end framework (such as Vue.js or React) integrated with a robust back-end (Node.js, Express, or Django). This application provides users with an intuitive interface to browse products, manage their shopping cart, place orders, and view order history. Administrators can add, edit, and manage product listings, process orders, and handle user accounts through an admin dashboard. The app features real-time updates, secure authentication, payment integration, and responsive design for a seamless shopping experience across devices. It combines a sleek, engaging UI with a scalable backend to support high traffic and data security.',
    imageUrl: 'https://images.unsplash.com/photo-1512436991641-6745cdb1723f?w=900&q=80',
    projectUrl: 'https://github.com/sandiliviwe04/TownshipsEats-App.git',
    platforms: ['Vue', 'Pinia', 'Tailwind'],
    tech: 'Shop UI',
    status: 'Demo',
  },
  {
    title: 'Hr-Management App Full-stack',
    description: 'A comprehensive HR management platform built with a modern front-end framework (such as Vue.js or React) connected to a scalable back-end (Node.js with Express, Django, or similar). The application provides an intuitive interface for HR teams and employees to manage and access critical HR functionalities, including employee profiles, attendance tracking, leave requests, payroll management, and reporting. The front-end offers a clean, responsive UI with interactive dashboards, forms, and data visualizations, while the back-end handles secure data storage, user authentication, role-based access control, and integration with third-party services (like payroll or email). The system is designed to be scalable, secure, and easy to maintain, streamlining HR workflows and improving organizational efficiency.',
    imageUrl: 'https://images.unsplash.com/photo-1522202176988-66273c2fd55f?w=900&q=80',
    projectUrl: 'https://github.com/Gazelle608/module_2_core_project.git',
    platforms: ['Vue', 'TypeScript', 'API'],
    tech: 'Productivity',
    status: 'Live',
  },
  {
    title: 'Oracle Appex App',
    description: 'A powerful, web-based application developed using Oracle Application Express (APEX), designed for rapid deployment and easy customization. This app leverages Oracle’s robust database capabilities to provide dynamic, secure, and scalable solutions tailored to specific business needs. With intuitive interfaces, interactive reports, forms, and dashboards, users can efficiently manage data, automate workflows, and generate insightful analytics—all within a browser. Oracle APEX’s declarative development environment ensures quick updates and maintenance, making it ideal for enterprise applications, data management, and process automation.',
    imageUrl: 'https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?w=900&q=80',
    projectUrl: 'https://oracleapex.com/ords/r/pluton/ot-smart-analytics-app/login?session=17121489368975',
    platforms: ['Vue', 'Fetch', 'API'],
    tech: 'Dashboard',
    status: 'Live',
  },
]
</script>

<style scoped>
.projects-section {
  padding: 10px 0;
}

.section-heading {
  text-align: center;
  margin-bottom: 32px;
  max-width: 820px;
  margin-left: auto;
  margin-right: auto;
}

.section-label {
  display: inline-block;
  font-size: 0.78rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  color: #38bdf8;
  margin-bottom: 0.85rem;
}

.section-heading h2 {
  color: #f8fafc;
  font-size: clamp(2rem, 2.5vw, 2.5rem);
  margin: 0.5rem 0 0.6rem;
}

.section-heading p {
  color: #cbd5e1;
  font-size: 0.98rem;
  line-height: 1.7;
  max-width: 680px;
  margin: 0 auto;
}

.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 24px;
}

.project-card {
  margin: 0;
}

.synth-card {
  position: relative;
  background: #0f0c29;
  border-radius: 16px;
  overflow: hidden;
  border: 2px solid #ff00ff;
  box-shadow:
    0 0 20px rgba(255, 0, 255, 0.25),
    0 0 40px rgba(0, 255, 255, 0.08),
    inset 0 0 16px rgba(255, 0, 255, 0.08);
}

.sunset-bg {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 58%;
  background: linear-gradient(to bottom, #ff00ff 0%, #ff0066 28%, #ff9900 58%, transparent 100%);
  opacity: 0.18;
  pointer-events: none;
}

.grid-floor {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 40%;
  background:
    linear-gradient(to bottom, transparent 0%, #0f0c29 100%),
    repeating-linear-gradient(
      90deg,
      transparent,
      transparent 48px,
      rgba(0, 255, 255, 0.1) 48px,
      rgba(0, 255, 255, 0.1) 49px
    );
  transform: perspective(500px) rotateX(60deg);
  transform-origin: bottom;
  opacity: 0;
  transition: opacity 0.3s ease;
  pointer-events: none;
}

.synth-card:hover .grid-floor {
  opacity: 1;
}

.scanlines {
  position: absolute;
  inset: 0;
  background: repeating-linear-gradient(
    0deg,
    transparent,
    transparent 2px,
    rgba(0, 0, 0, 0.22) 2px,
    rgba(0, 0, 0, 0.22) 4px
  );
  pointer-events: none;
  z-index: 10;
  opacity: 0.26;
}

.card-inner {
  position: relative;
  z-index: 2;
  background: rgba(15, 12, 41, 0.95);
  border-radius: 16px;
  overflow: hidden;
}

.image-wrapper {
  position: relative;
  height: 235px;
  overflow: hidden;
}

.retro-border {
  position: absolute;
  inset: 15px;
  pointer-events: none;
  z-index: 5;
}

.border-segment {
  position: absolute;
  background: #00ffff;
  box-shadow: 0 0 10px #00ffff;
  transition: transform 0.4s ease;
}

.border-segment.top {
  top: 0;
  left: 0;
  right: 0;
  height: 2px;
  transform: scaleX(0);
  transform-origin: left;
}

.border-segment.right {
  top: 0;
  right: 0;
  bottom: 0;
  width: 2px;
  transform: scaleY(0);
  transform-origin: top;
}

.border-segment.bottom {
  bottom: 0;
  left: 0;
  right: 0;
  height: 2px;
  transform: scaleX(0);
  transform-origin: right;
}

.border-segment.left {
  top: 0;
  left: 0;
  bottom: 0;
  width: 2px;
  transform: scaleY(0);
  transform-origin: bottom;
}

.synth-card:hover .border-segment {
  transform: scale(1);
}

.image-container {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.project-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
  filter: saturate(1.15) contrast(1.1);
}

.synth-card:hover .project-image {
  transform: scale(1.08);
}

.crt-overlay {
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at center, transparent 48%, rgba(0, 0, 0, 0.4) 100%);
  pointer-events: none;
}

.chromatic-aberration {
  position: absolute;
  inset: 0;
  background: linear-gradient(45deg, rgba(255, 0, 0, 0.1) 0%, transparent 50%, rgba(0, 255, 255, 0.1) 100%);
  mix-blend-mode: screen;
  animation: chromaticShift 0.5s infinite;
  pointer-events: none;
}

@keyframes chromaticShift {
  0%, 100% { transform: translate(0); }
  25% { transform: translate(2px, 0); }
  75% { transform: translate(-2px, 0); }
}

.image-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(15, 12, 41, 0.95) 0%, transparent 100%);
  opacity: 0;
  transition: opacity 0.3s ease;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  padding: 24px;
}

.synth-card:hover .image-overlay {
  opacity: 1;
}

.overlay-content {
  transform: translateY(20px);
  opacity: 0;
  transition: all 0.4s ease 0.1s;
}

.synth-card:hover .overlay-content {
  transform: translateY(0);
  opacity: 1;
}

.game-stats {
  display: flex;
  gap: 14px;
  margin-bottom: 18px;
}

.stat-box {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 14px;
  background: rgba(0, 0, 0, 0.6);
  border: 1px solid rgba(0, 255, 255, 0.25);
  border-radius: 999px;
}

.stat-icon {
  font-size: 1rem;
}

.stat-val {
  color: #00ffff;
  font-weight: 700;
  font-size: 0.86rem;
  text-shadow: 0 0 10px #00ffff;
}

.play-button {
  display: flex;
  align-items: center;
  gap: 12px;
  cursor: pointer;
}

.play-icon {
  width: 46px;
  height: 46px;
  border-radius: 50%;
  background: linear-gradient(135deg, #ff00ff 0%, #ff0066 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  box-shadow: 0 0 18px rgba(255, 0, 255, 0.55);
  transition: transform 0.3s ease;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% { box-shadow: 0 0 18px rgba(255, 0, 255, 0.5); }
  50% { box-shadow: 0 0 34px rgba(255, 0, 255, 0.85); }
}

.play-button:hover .play-icon {
  transform: scale(1.08);
}

.play-text {
  color: #fff;
  font-weight: 800;
  font-size: 0.95rem;
  letter-spacing: 0.08em;
  text-shadow: 0 0 10px rgba(255, 0, 255, 0.8);
}

.floating-particles {
  position: absolute;
  inset: 0;
  pointer-events: none;
  overflow: hidden;
}

.particle {
  position: absolute;
  width: 4px;
  height: 4px;
  background: #00ffff;
  border-radius: 50%;
  box-shadow: 0 0 10px #00ffff;
  animation: floatUp 3s infinite;
  animation-delay: calc(var(--i) * 0.4s);
  left: calc(var(--i) * 16.66%);
  bottom: -8px;
  opacity: 0;
}

.synth-card:hover .particle {
  opacity: 1;
}

@keyframes floatUp {
  0% { transform: translateY(0) scale(0); opacity: 0; }
  50% { opacity: 1; }
  100% { transform: translateY(-190px) scale(1); opacity: 0; }
}

.project-info {
  padding: 24px;
  background: linear-gradient(to bottom, transparent 0%, rgba(15, 12, 41, 0.9) 100%);
}

.glitch-title {
  position: relative;
  margin-bottom: 12px;
}

.project-title {
  font-size: 1.45rem;
  font-weight: 900;
  color: #fff;
  margin: 0;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  position: relative;
  z-index: 2;
  text-shadow: 0 0 10px #ff00ff, 0 0 20px #ff00ff, 0 0 30px #ff00ff;
}

.glitch-shadow,
.glitch-shadow-2 {
  position: absolute;
  top: 0;
  left: 0;
  font-size: 1.45rem;
  font-weight: 900;
  color: #ff00ff;
  opacity: 0;
  letter-spacing: 0.06em;
  text-transform: uppercase;
}

.glitching .glitch-shadow {
  animation: glitch-1 0.3s infinite;
  opacity: 0.8;
  color: #0ff;
  z-index: 1;
}

.glitching .glitch-shadow-2 {
  animation: glitch-2 0.3s infinite;
  opacity: 0.8;
  color: #ff0066;
  z-index: 1;
}

@keyframes glitch-1 {
  0%, 100% { transform: translate(0); }
  20% { transform: translate(-3px, 3px); }
  40% { transform: translate(-3px, -3px); }
  60% { transform: translate(3px, 3px); }
  80% { transform: translate(3px, -3px); }
}

@keyframes glitch-2 {
  0%, 100% { transform: translate(0); }
  20% { transform: translate(3px, -3px); }
  40% { transform: translate(3px, 3px); }
  60% { transform: translate(-3px, -3px); }
  80% { transform: translate(-3px, 3px); }
}

.project-description {
  font-size: 0.94rem;
  color: #cbd5e1;
  line-height: 1.7;
  margin-bottom: 18px;
}

.platform-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-bottom: 20px;
}

.platform {
  padding: 6px 12px;
  background: rgba(0, 255, 255, 0.12);
  border: 1px solid rgba(0, 255, 255, 0.2);
  border-radius: 999px;
  font-size: 0.75rem;
  color: #22d3ee;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

.card-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 16px;
}

.synth-btn {
  position: relative;
  display: inline-flex;
  align-items: center;
  padding: 14px 24px;
  background: transparent;
  color: #fff;
  border: 2px solid #00ffff;
  border-radius: 999px;
  text-decoration: none;
  font-weight: 800;
  font-size: 0.85rem;
  letter-spacing: 0.1em;
  overflow: hidden;
  transition: all 0.3s ease;
  text-transform: uppercase;
}

.btn-glow {
  position: absolute;
  inset: 0;
  background: linear-gradient(90deg, #ff00ff, #00ffff, #ff00ff);
  background-size: 200% 100%;
  opacity: 0;
  transition: opacity 0.3s ease;
  z-index: 0;
  animation: glowMove 2.2s linear infinite;
}

@keyframes glowMove {
  0% { background-position: 0% 50%; }
  100% { background-position: 200% 50%; }
}

.synth-btn:hover .btn-glow {
  opacity: 0.22;
}

.synth-btn:hover {
  border-color: #ff00ff;
  box-shadow: 0 0 18px rgba(255, 0, 255, 0.35), inset 0 0 12px rgba(255, 0, 255, 0.1);
  transform: translateY(-1px);
}

.btn-text {
  position: relative;
  z-index: 1;
  text-shadow: 0 0 10px rgba(0, 255, 255, 0.8);
}

.price-tag {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

.original {
  font-size: 0.8rem;
  color: #94a3b8;
}

.sale {
  font-size: 1rem;
  font-weight: 900;
  color: #22d3ee;
  text-shadow: 0 0 10px #22d3ee;
}
</style>
