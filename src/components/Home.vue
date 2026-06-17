<script setup>
import { ref, onMounted } from 'vue'

const roles = ['Frontend Developer', 'Vue.js Developer', 'Creative Coder','React Developer']
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
  <Component is="style">
    @import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Playfair+Display:ital,wght@0,600;1,400&family=Plus+Jakarta+Sans:wght@400;500&display=swap');
  </Component>

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
  padding: 40px 16px;
  /* Crisp secondary font fallback for default paragraph text */
  font-family: 'Plus Jakarta Sans', sans-serif;
}

/* subtle glowing background */
.overlay {
  position: absolute;
  top: -40px;
  left: 50%;
  width: 520px;
  height: 520px;
  transform: translateX(-50%);
  background: radial-gradient(circle, rgba(59, 130, 246, 0.35), transparent);
  filter: blur(120px);
  animation: float 6s ease-in-out infinite;
}

@keyframes float {
  0%, 100% {
    transform: translateX(-50%) translateY(0);
  }
  50% {
    transform: translateX(-50%) translateY(-40px);
  }
}

.content {
  text-align: center;
  z-index: 1;
  max-width: min(700px, 100%);
  padding: 20px;
}

/* ==========================================================================
   TYPOGRAPHY CONFIGURATION (CURSIVE & SERIF UPDATES)
   ========================================================================== */
.intro {
  font-family: 'Pacifico', cursive; /* Modern signature cursive style */
  font-size: 22px; /* Bumped slightly to balance the script height */
  color: #60a5fa;
  margin-bottom: 5px;
}

.name {
  font-family: 'Playfair Display', serif; /* Elegant high-end display heading */
  font-size: clamp(2.75rem, 7vw, 4.5rem);
  font-weight: 600;
  letter-spacing: -0.5px;
  margin: 10px 0;
  background: linear-gradient(to right, #3b82f6, #c084fc);
  -webkit-background-clip: text;
  color: transparent;
}

.role {
  font-family: 'Pacifico', cursive; /* Makes the typing effect display in script font */
  font-size: clamp(1.4rem, 3vw, 2.2rem);
  font-weight: 400;
  color: #e2e8f0;
  margin-bottom: 20px;
}

.cursor {
  font-family: sans-serif; /* Prevents the script font from bending your indicator bar */
  font-weight: 100;
  color: #3b82f6;
  animation: blink 1s infinite;
}

@keyframes blink {
  50% { opacity: 0; }
}

.description {
  font-size: 16px;
  line-height: 1.6;
  opacity: 0.8;
  margin-bottom: 30px;
}

/* ==========================================================================
   BUTTONS
   ========================================================================== */
.buttons {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 15px;
}

button,
.buttons a {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 12px 24px;
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
  transform: scale(1.03);
}

.secondary {
  background: transparent;
  border: 1px solid #3b82f6;
  color: #3b82f6;
}

.secondary:hover {
  background: #3b82f6;
  color: white;
  transform: scale(1.03);
}

/* ==========================================================================
   RESPONSIVE DESIGN BREAKPOINTS
   ========================================================================== */
@media (max-width: 768px) {
  .home {
    padding: 50px 14px 30px;
  }

  .overlay {
    width: 420px;
    height: 420px;
    top: -30px;
  }

  .description {
    font-size: 15px;
  }

  .buttons {
    flex-direction: column;
    align-items: center;
  }
}

@media (max-width: 480px) {
  .home {
    padding: 40px 12px 24px;
  }

  .overlay {
    width: 300px;
    height: 300px;
    top: -20px;
  }

  .intro {
    font-size: 18px;
  }

  .description {
    font-size: 14px;
  }
}
</style>