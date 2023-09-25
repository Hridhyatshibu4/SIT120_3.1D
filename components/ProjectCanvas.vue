<template>
  <div>
    <h2>Project Canvas</h2>

    <!-- Canvas Graphic -->
    <canvas id="canvas" width="400" height="300"></canvas>

    <!-- SVG Graphic -->
    <svg xmlns="http://www.w3.org/2000/svg" width="400" height="300">
      <!-- Background Rectangle -->
      <rect x="0" y="0" width="100%" height="100%" fill="#f0f0f0" />

      <!-- Employee Drawing -->
      <circle cx="150" cy="150" r="10" fill="blue" />
      <line x1="150" y1="150" x2="200" y2="200" stroke="blue" stroke-width="3" />
      <line x1="200" y1="200" x2="250" y2="150" stroke="blue" stroke-width="3" />
      <rect x="220" y="180" width="30" height="30" fill="green" />
    </svg>
    
    <!-- Add your content for the project canvas here -->
  </div>
</template>

<script>
export default {
  name: 'ProjectCanvas',
  mounted() {
    // JavaScript logic for working with the Canvas graphic
    const canvas = document.getElementById('canvas');
    const context = canvas.getContext('2d');
    context.fillStyle = 'white';
    context.fillRect(0, 0, canvas.width, canvas.height);

    // JavaScript logic for working with the SVG graphic
    // You can use libraries like D3.js or manipulate SVG elements directly
  },
}
</script>

<style>
/* Add your CSS styles for the project canvas here */

/* Center the canvas and SVG */
div {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

h2 {
  font-size: 24px;
  margin-bottom: 20px;
}

/* Style the canvas */
canvas {
  border: 1px solid #ccc;
  margin-bottom: 20px;
}

/* Style the SVG container */
svg {
  border: 1px solid #ccc;
}

/* Style SVG elements */
circle {
  fill: blue;
}

line {
  stroke: blue;
  stroke-width: 3;
}

rect {
  fill: green;
}

/* Add more styles as needed for your specific design */
</style>

