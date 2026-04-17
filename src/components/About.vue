<template>
  <section id="About" class="about-section">
    <div class="about-container">

      <!-- LEFT SIDE -->
      <div class="about-text">
        <h2>About Me</h2>

        <p>
          Hi, I'm <span class="highlight">Khangelani</span> — a passionate 
          <strong>Frontend Developer</strong> who builds modern, responsive, 
          and user-friendly web applications.
        </p>

        <p>
          I enjoy turning ideas into real products and creating clean UI with 
          smooth user experiences.
        </p>

        <div class="tags">
          <span>Vue.js</span>
          <span>JavaScript</span>
          <span>Python</span>
          <span>SQL</span>
          <span>HTML</span>
          <span>CSS</span>
          <span>Oracle Apex</span>
        </div>

        <a href="/downloads/cv.pdf" download class="download-btn">
          ⬇ Download CV
        </a>
      </div>

      <!-- RIGHT SIDE -->
      <div class="about-card">
        <div class="card">
          <p>💻 2+ Projects Built</p>
          <p>⚡ Frontend Specialist</p>
          <p>🚀 Always Learning</p>
        </div>
      </div>

    </div>
  </section>
</template>
<style>
.about-section {
  padding: 80px 20px;
  color: white;
}

.about-container {
  max-width: 1100px;
  margin: auto;
  display: flex;
  align-items: center;
  gap: 50px;
  flex-wrap: wrap;
}

/* LEFT SIDE */
.about-text {
  flex: 1;
}

.about-text h2 {
  font-size: 36px;
  margin-bottom: 20px;
}

.about-text p {
  font-size: 16px;
  opacity: 0.8;
  line-height: 1.6;
  margin-bottom: 15px;
}

.highlight {
  color: #3b82f6;
}

/* TAGS */
.tags {
  margin: 20px 0;
}

.tags span {
  display: inline-block;
  background: rgba(59, 130, 246, 0.2);
  color: #3b82f6;
  padding: 6px 12px;
  border-radius: 20px;
  margin: 5px;
  font-size: 13px;
  transition: 0.3s;
}

.tags span:hover {
  background: #3b82f6;
  color: white;
}

/* BUTTON */
.download-btn {
  display: inline-block;
  margin-top: 15px;
  padding: 12px 25px;
  border-radius: 30px;
  background: #3b82f6;
  color: white;
  text-decoration: none;
  transition: 0.3s;
}

.download-btn:hover {
  transform: scale(1.05);
  background: #2563eb;
}

/* RIGHT SIDE CARD */
.about-card {
  flex: 1;
  display: flex;
  justify-content: center;
}

.card {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(12px);
  padding: 30px;
  border-radius: 20px;
  width: 250px;
  text-align: center;
  border: 1px solid rgba(255,255,255,0.1);
  transition: 0.3s;
}

.card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(59, 130, 246, 0.3);
}

.card p {
  margin: 10px 0;
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .about-container {
    flex-direction: column;
    text-align: center;
  }
}
</style>