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

@media (max-width: 640px) {
  nav {
    gap: 10px;
  }

  .nav-links {
    width: 100%;
    justify-content: center;
  }

  a {
    padding: 10px 12px;
    font-size: 0.95rem;
  }
}
</style>
