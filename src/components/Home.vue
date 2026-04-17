<script setup>
import { ref, onMounted } from 'vue'

const roles = ['Frontend Developer', 'Vue.js Developer', 'Creative Coder']
const currentRole = ref('')
let index = 0
let charIndex = 0

function typeEffect() {
  if (charIndex < roles[index].length) {
    currentRole.value += roles[index].charAt(charIndex)
    charIndex++
    setTimeout(typeEffect, 80)
  } else {
    setTimeout(() => {
      currentRole.value = ''
      charIndex = 0
      index = (index + 1) % roles.length
      typeEffect()
    }, 1500)
  }
}

onMounted(() => {
  typeEffect()
})
</script>

<template>
  <section id="Home" class="home">
    <div class="overlay"></div>

    <div class="content">
      <p class="intro">👋 Greetings by</p>
      <h1 class="name">Khangelani Mhlakane</h1>

      <h2 class="role">{{ currentRole }}<span class="cursor">|</span></h2>

      <p class="description">
        I build modern, responsive, and user-friendly web applications. Passionate about crafting
        clean UI and smooth user experiences.
      </p>

      <div class="buttons">
        <a href="#Projects" class="primary">View Projects</a>
        <a href="#Contact" class="secondary">Contact Me</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.home {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, #0f172a, #1e293b);
  color: white;
  position: relative;
  overflow: hidden;
}

/* subtle glowing background */
.overlay {
  position: absolute;
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, rgba(59, 130, 246, 0.4), transparent);
  filter: blur(120px);
  animation: float 6s ease-in-out infinite;
}

@keyframes float {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-40px);
  }
}

.content {
  text-align: center;
  z-index: 1;
  max-width: 700px;
  padding: 20px;
}

/* typography */
.intro {
  font-size: 18px;
  opacity: 0.7;
}

.name {
  font-size: 60px;
  font-weight: bold;
  margin: 10px 0;
  background: linear-gradient(to right, #3b82f6, #9333ea);
  -webkit-background-clip: text;
  color: transparent;
}

.role {
  font-size: 28px;
  margin-bottom: 15px;
}

.cursor {
  animation: blink 1s infinite;
}

@keyframes blink {
  50% {
    opacity: 0;
  }
}

.description {
  font-size: 16px;
  opacity: 0.8;
  margin-bottom: 25px;
}

/* buttons */
.buttons {
  display: flex;
  justify-content: center;
  gap: 15px;
}

button,
.buttons a {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 12px 25px;
  border-radius: 30px;
  border: none;
  cursor: pointer;
  transition: 0.3s;
  font-weight: 500;
  text-decoration: none;
}

.primary {
  background: #3b82f6;
  color: white;
}

.primary:hover {
  background: #2563eb;
  transform: scale(1.05);
}

.secondary {
  background: transparent;
  border: 1px solid #3b82f6;
  color: #3b82f6;
}

.secondary:hover {
  background: #3b82f6;
  color: white;
  transform: scale(1.05);
}

/* responsive */
@media (max-width: 768px) {
  .name {
    font-size: 40px;
  }

  .role {
    font-size: 20px;
  }
}
</style>
