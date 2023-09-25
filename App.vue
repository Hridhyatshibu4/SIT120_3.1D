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
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
