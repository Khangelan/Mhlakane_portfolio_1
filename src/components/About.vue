<template>
  <section id="About" class="about-section">
    <div class="about-container">

      <div class="about-text">
        <h2>About Me</h2>

        <p>
          Hi, I'm <span class="highlight">Khangelani Mhlakane</span> — a passionate 
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
          <span>React</span>
          <span>Git & Git Bash</span>
          <span>Typescript</span>
          <span>Oracle Apex</span>
        </div>

        <a href="/downloads/Khangelani Mhlakane-CV " download class="download-btn">
          <i class="fa-solid fa-arrow-down-to-bracket"></i> Download CV
        </a>
      </div>

      <div class="about-card">
        <div class="card">
          <div class="card-item">
            <i class="fa-solid fa-laptop-code icon-blue"></i>
            <span>2+ Projects Built</span>
          </div>
          
          <div class="card-item">
            <i class="fa-solid fa-bolt icon-purple"></i>
            <span>Frontend Specialist</span>
          </div>
          
          <div class="card-item">
            <i class="fa-solid fa-rocket icon-orange"></i>
            <span>Always Learning</span>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
/* Scoped ensures this doesn't leak into other parts of your site */
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
  min-width: 300px;
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

/* DOWNLOAD BUTTON */
.download-btn {
  display: inline-flex;
  align-items: center;
  gap: 10px; /* Space between the download tray and text */
  margin-top: 15px;
  padding: 12px 25px;
  border-radius: 30px;
  background: #3b82f6;
  color: white;
  font-weight: 500;
  text-decoration: none;
  transition: 0.3s;
}

.download-btn:hover {
  transform: scale(1.05);
  background: #2563eb;
}

/* RIGHT SIDE CARD STRUCTURE */
.about-card {
  flex: 1;
  display: flex;
  justify-content: center;
  min-width: 280px;
}

.card {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  padding: 30px;
  border-radius: 20px;
  width: 280px; /* Shifted slightly up from 250px to fit full text rows nicely */
  border: 1px solid rgba(255, 255, 255, 0.1);
  display: flex;
  flex-direction: column;
  gap: 20px; /* Clean, uniform distribution spacing */
  transition: 0.3s ease;
}

.card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(59, 130, 246, 0.25);
}

/* ALIGNS ICON AND LABEL IN LINE */
.card-item {
  display: flex;
  align-items: center;
  gap: 14px;
  font-size: 16px;
  font-weight: 500;
  color: #ccd6f6;
  text-align: left; /* Tidy horizontal line-up */
}

/* Forces icons to sit perfectly center on a fixed column grid width */
.card-item i {
  font-size: 20px;
  width: 25px;
  text-align: center;
}

/* Accent complementary colors for individual icons */
.icon-blue {
  color: #3b82f6;
}

.icon-purple {
  color: #a855f7;
}

.icon-orange {
  color: #f97316;
}

/* RESPONSIVE LAYOUT STACK */
@media (max-width: 768px) {
  .about-container {
    flex-direction: column;
    text-align: center;
  }
  
  .card-item {
    justify-content: center; /* Centers items nicely inside the card profile on mobile screens */
  }
  
  .download-btn {
    margin: 20px auto 0 auto;
  }
}
</style>