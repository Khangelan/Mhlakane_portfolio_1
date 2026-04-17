<template>
  <section id="Experience" class="experience-section">
    <div class="experience-header">
      <span class="section-label">Work History</span>
      <h2>Experience</h2>
      <p>Practical experience gained through roles, internships, and real projects, showing the impact I deliver.</p>
    </div>

    <div class="experience-grid">
      <article class="experience-card">
        <div class="experience-meta">
          <span class="role">Full-stack Web developer </span>
          <span class="company">Life Choices (Trainee)</span>
        </div>
        <p class="duration">2025/08 - 2026/03</p>
        <ul>
          <li>Built responsive web applications with Vue 3 and modern CSS.</li>
          <li>Designed UI flows, landing pages, and interactive dashboards.</li>
          <li>Improved performance and accessibility for Company projects.</li>
        </ul>
      </article>
      <article class="experience-card">
        <div class="experience-meta">
          <span class="role">Full-stack Web Developer</span>
          <span class="company">Life choices (Intern)</span>
        </div>
        <p class="duration">2026 - Present</p>
        <ul>
            <li>Gained foundational experience in Microsoft Azure Machine Learning, including building, training, and evaluating basic ML models in a cloud environment.</li>
            <li>Understood core machine learning concepts such as data preparation, supervised learning, and model deployment using Azure tools.</li>
            <li>Developed awareness of how cloud-based AI services are used to build scalable and data-driven solutions.</li>
        </ul>
      </article>
    </div>
  </section>
</template>

<style scoped>
.experience-section {
  padding: 42px 24px;
  background: linear-gradient(180deg, rgba(15, 23, 42, 0.98), rgba(30, 41, 59, 0.95));
  border-radius: 28px;
}

.experience-header {
  text-align: center;
  max-width: 720px;
  margin: 0 auto 38px;
}

.section-label {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  background: rgba(14, 165, 233, 0.15);
  color: #38bdf8;
  border-radius: 999px;
  text-transform: uppercase;
  letter-spacing: 0.24em;
  font-size: 0.78rem;
  margin-bottom: 16px;
}

.experience-header h2 {
  font-size: clamp(2rem, 2.6vw, 2.4rem);
  margin: 0 0 14px;
  color: #f8fafc;
}

.experience-header p {
  color: #cbd5e1;
  line-height: 1.75;
  max-width: 640px;
  margin: 0 auto;
}

.experience-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 24px;
}

.experience-card {
  position: relative;
  padding: 26px;
  border-radius: 24px;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.08);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.18);
  transition: transform 0.3s ease, border-color 0.3s ease;
}

.experience-card:hover {
  transform: translateY(-8px);
  border-color: rgba(56, 189, 248, 0.4);
}

.experience-meta {
  display: flex;
  flex-direction: column;
  gap: 6px;
  margin-bottom: 16px;
}

.role {
  font-size: 1.15rem;
  font-weight: 700;
  color: #fff;
}

.company {
  color: #60a5fa;
  font-size: 0.95rem;
}

.duration {
  margin: 0 0 18px;
  color: #93c5fd;
  font-size: 0.95rem;
}

.experience-card ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: grid;
  gap: 12px;
}

.experience-card li {
  color: #cbd5e1;
  line-height: 1.75;
  position: relative;
  padding-left: 24px;
}

.experience-card li::before {
  content: "•";
  position: absolute;
  left: 0;
  top: 0;
  color: #22d3ee;
}

@media (max-width: 640px) {
  .experience-section {
    padding: 32px 18px;
  }
}
</style>
