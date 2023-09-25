<template>
  <div>
    <h2>Navigation Map</h2>

    <!-- Google Maps iframe -->
    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3151.996085586444!2d145.11571277535967!3d-37.81356067197571!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x6ad640b42896b6b1%3A0x59c42fd65a565506!2sBox%20Hill%20Hospital!5e0!3m2!1sen!2sau!4v1695611331290!5m2!1sen!2sau" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>

    <!-- Add your content for the navigation map here -->
  </div>
</template>

<script>
export default {
  name: 'NavigationMap',
}
</script>

<style>
/* Add your CSS styles for the navigation map here */
/* You can style the container or iframe as needed */
div {
  text-align: center;
  margin-top: 20px;
}

h2 {
  font-size: 24px;
  margin-bottom: 20px;
}

iframe {
  border: 1px solid #ccc;
}
</style>
