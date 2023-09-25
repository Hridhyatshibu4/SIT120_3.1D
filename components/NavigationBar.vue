<!-- NavBar.vue -->
<template>
  <nav class="navbar">
    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/goals-and-achievements">Goals & Achievements</router-link></li>
      <li><router-link to="/learning-module">Learning Module</router-link></li>
      <li><router-link to="/project-canvas">Project Canvas</router-link></li>
      <li><router-link to="/navigation-map">Navigation Map</router-link></li>
      <li><router-link to="/chat-portal">Chat Portal</router-link></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'NavBar'
}
</script>

<style scoped>
/* Add your CSS styles for the navigation bar here */
</style>
