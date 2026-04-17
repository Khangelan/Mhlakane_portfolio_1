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
  gap: 16px;
}

a {
  text-decoration: none;
  color: inherit;
  font-weight: 600;
  font-size: 1.05em;
  padding: 8px 16px;
  border-radius: 6px;
  transition:
    background-color 0.3s,
    color 0.3s;
}

a:hover {
  opacity: 0.9;
}
</style>
