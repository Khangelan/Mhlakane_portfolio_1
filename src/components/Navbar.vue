<script setup>
const props = defineProps({
  isLightMode: {
    type: Boolean,
    default: false,
  },
})

const emit = defineEmits(['toggle-theme'])
</script>

<template>
  <nav>
    <div class="nav-links">
      <a href="#Home">Home</a>
      <a href="#About">About</a>
      <a href="#Experience">Experience</a>
      <a href="#Projects">Projects</a>
      <a href="#Certificates">Certificates</a>
      <a href="#Contact">Contact</a>
    </div>
    <button class="theme-toggle" type="button" @click="emit('toggle-theme')">
      <span v-if="props.isLightMode">🌙 Dark mode</span>
      <span v-else>☀️ Light mode</span>
    </button>
  </nav>
</template>

<style scoped>
nav {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
}

.nav-links {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  justify-content: center;
}

a {
  text-decoration: none;
  color: inherit;
  font-weight: 600;
  font-size: 1rem;
  padding: 8px 14px;
  border-radius: 6px;
  transition:
    background-color 0.3s,
    color 0.3s,
    transform 0.3s;
}

a:hover {
  opacity: 0.95;
  transform: translateY(-1px);
}

.theme-toggle {
  border: none;
  background: rgba(255, 255, 255, 0.15);
  color: inherit;
  padding: 8px 16px;
  border-radius: 999px;
  cursor: pointer;
  font-weight: 700;
  transition: transform 0.3s, background-color 0.3s;
}

.theme-toggle:hover {
  transform: translateY(-1px);
  background: rgba(255, 255, 255, 0.25);
}

@media (max-width: 640px) {
  nav {
    gap: 10px;
  }

  .nav-links {
    width: 100%;
    justify-content: center;
  }

  a,
  .theme-toggle {
    padding: 10px 12px;
    font-size: 0.95rem;
  }
}
</style>
