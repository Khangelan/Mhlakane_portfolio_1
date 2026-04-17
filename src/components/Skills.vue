<template>
  <section id="Skills" class="skills-section">
    <h2>My Skills</h2>
    <div class="skills-container">
      <div class="skill-card">
        <i class="fab fa-html5"></i>
        <h3>HTML5</h3>
        <p>Markup language for structuring web content</p>
      </div>
      <div class="skill-card">
        <i class="fab fa-css3-alt"></i>
        <h3>CSS3</h3>
        <p>Styling language for designing web layouts</p>
      </div>
      <div class="skill-card">
        <i class="fab fa-js"></i>
        <h3>JavaScript</h3>
        <p>Programming language for interactive web development</p>
      </div>
      <div class="skill-card">
        <i class="fab fa-vuejs"></i>
        <h3>Vue.js</h3>
        <p>Progressive framework for building user interfaces</p>
      </div>
      <div class="skill-card">
        <i class="fab fa-react"></i>
        <h3>React</h3>
        <p>Library for building dynamic user interfaces</p>
      </div>
      <div class="skill-card">
        <i class="fab fa-node-js"></i>
        <h3>Node.js</h3>
        <p>Runtime for server-side JavaScript applications</p>
      </div>
      <div class="skill-card">
        <i class="fab fa-python"></i>
        <h3>Python</h3>
        <p>Versatile language for web, data, and automation</p>
      </div>
      <div class="skill-card">
        <i class="fab fa-git-alt"></i>
        <h3>Git</h3>
        <p>Version control system for tracking code changes</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.skills-section {
  padding: 40px 20px;
  background-color: #f9f9f9;
  max-width: 1200px;
  margin: 40px auto;
  border-radius: 10px;
  text-align: center;
}

h2 {
  margin-bottom: 40px;
  font-size: 2.5em;
  color: #333;
  font-weight: bold;
}

.skills-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 30px;
  justify-items: center;
}

.skill-card {
  background: white;
  border-radius: 15px;
  padding: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  width: 100%;
  max-width: 250px;
}

.skill-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.skill-card i {
  font-size: 3em;
  color: #42b983;
  margin-bottom: 15px;
}

.skill-card h3 {
  font-size: 1.2em;
  margin: 10px 0;
  color: #333;
}

.skill-card p {
  font-size: 0.9em;
  color: #666;
  margin: 0;
}
</style>