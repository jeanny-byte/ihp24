<template>
 <div class="transparent-image-component">
    <!-- Use an empty div with a background image -->
    <div class="background-image"></div>

    <!-- Your component content goes here -->
    <!-- For example, add text or other elements -->
  
  </div>
</template>

<script>


export default {
  name: 'IHP24',
  components: {
    
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.transparent-image-component {
  /* Set component styles here */
}

.background-image {
  position: center;
  margin: auto;
  background-image: url('./assets/transparent-image.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-color: transparent;
  width: 60%; /* Adjust the width as needed */
  height: 100vh; /* Adjust the height as needed */
  opacity: 0.2; /* Adjust the opacity to control transparency */
  /* Add other styles as necessary */
}
</style>
