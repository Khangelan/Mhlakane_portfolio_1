<template>
  <section id="Certificates" class="certificates-section">
    <div class="section-header">
      <span class="section-label">Learning Journey</span>
      <h2>Certificates & Courses</h2>
      <p>Selected credentials that highlight my technical growth, certifications, and practical skills.</p>
    </div>

    <div class="certificate-grid">
      <article class="certificate-card">
        <div class="card-top">
          <span class="card-badge">01</span>
          <span class="card-tag">Web</span>
        </div>
        <h3>Youthcode Front-End Developer</h3>
        <p class="issuer">Youthcode</p>
        <p>Completed a certificate focused on HTML, CSS, JavaScript, Vue.js, and responsive web development best practices.</p>
      </article>

      <article class="certificate-card">
        <div class="card-top">
          <span class="card-badge">02</span>
          <span class="card-tag">Security</span>
        </div>
        <h3>Introduction to Cybersecurity</h3>
        <p class="issuer">Cisco</p>
        <p>Built core cybersecurity knowledge in threat types, secure practices, and the CIA triad for defending systems and data.</p>
      </article>

      <article class="certificate-card">
        <div class="card-top">
          <span class="card-badge">03</span>
          <span class="card-tag">Data</span>
        </div>
        <h3>Introduction to Data Science</h3>
        <p class="issuer">Cisco</p>
        <p>Learned data collection, cleaning, analysis, and visualization workflows to turn raw data into decision-ready insights.</p>
      </article>

      <article class="certificate-card">
        <div class="card-top">
          <span class="card-badge">04</span>
          <span class="card-tag">AI</span>
        </div>
        <h3>Azure Machine Learning</h3>
        <p class="issuer">freeCodeCamp</p>
        <p>Studied Azure tools for training, evaluating, and deploying machine learning models in a cloud-based environment.</p>
      </article>
    </div>
  </section>
</template>

<style scoped>
.certificates-section {
  padding: 48px 24px;
  background: linear-gradient(180deg, rgba(15, 23, 42, 0.96), rgba(14, 30, 60, 0.98));
  border-radius: 30px;
  box-shadow: inset 0 0 100px rgba(255, 255, 255, 0.02);
}

.section-header {
  text-align: center;
  max-width: 760px;
  margin: 0 auto 40px;
}

.section-label {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  background: rgba(56, 189, 248, 0.12);
  color: #38bdf8;
  border-radius: 999px;
  text-transform: uppercase;
  letter-spacing: 0.24em;
  font-size: 0.78rem;
  margin-bottom: 18px;
}

h2 {
  font-size: clamp(2rem, 2.8vw, 2.6rem);
  margin: 0 0 14px;
  color: #f8fafc;
}

.section-header p {
  color: #cbd5e1;
  line-height: 1.75;
  max-width: 640px;
  margin: 0 auto;
}

.certificate-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 26px;
}

.certificate-card {
  position: relative;
  overflow: hidden;
  border-radius: 24px;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.08);
  padding: 28px;
  box-shadow: 0 30px 60px rgba(0, 0, 0, 0.28);
  transition: transform 0.35s ease, border-color 0.35s ease, box-shadow 0.35s ease;
}

.certificate-card::before {
  content: "";
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at top left, rgba(56, 189, 248, 0.18), transparent 35%),
              radial-gradient(circle at bottom right, rgba(139, 92, 246, 0.14), transparent 30%);
  pointer-events: none;
}

.certificate-card:hover {
  transform: translateY(-8px);
  border-color: rgba(56, 189, 248, 0.4);
  box-shadow: 0 36px 80px rgba(0, 0, 0, 0.36);
}

.card-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 20px;
  gap: 12px;
}

.card-badge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 42px;
  height: 42px;
  border-radius: 50%;
  background: #2563eb;
  color: #fff;
  font-weight: 700;
}

.card-tag {
  padding: 6px 14px;
  border-radius: 999px;
  background: rgba(99, 102, 241, 0.18);
  color: #e0e7ff;
  font-size: 0.82rem;
  font-weight: 600;
}

.certificate-card h3 {
  margin: 0 0 10px;
  font-size: 1.35rem;
  color: #fff;
  line-height: 1.25;
}

.issuer {
  margin-bottom: 16px;
  color: #93c5fd;
  font-size: 0.95rem;
}

.certificate-card p {
  color: #cbd5e1;
  line-height: 1.8;
  font-size: 0.95rem;
  margin: 0;
}

@media (max-width: 640px) {
  .certificates-section {
    padding: 32px 18px;
  }

  .card-top {
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>
