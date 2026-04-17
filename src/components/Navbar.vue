<template>
  <nav>
    <a href="#Home">Home</a>
    <a href="#About">About</a>
    <a href="#Experience">Experience</a>
    <a href="#Projects">Projects</a>
    <a href="#Certificates">Certificates</a>
    <a href="#Contact">Contact</a>
  </nav>
</template>

<style scoped>
.navbar {
  display: flex;
  gap: 20px;
  background-color: #1e3a8a; /* Deep blue background */
  padding: 15px 30px;
  justify-content: center; /* Center the links */
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);

}

a {
  text-decoration: none;
  color: #6b7294; /* White text for contrast */
  font-weight: 600;
  font-size: 1.1em;
  padding: 8px 16px;
  border-radius: 4px;
  transition: background-color 0.3s, color 0.3s;
}

a:hover {
  background-color: #3b82f6; /* Lighter blue on hover */
  color: #ffffff;
}
</style>