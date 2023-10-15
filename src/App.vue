<template>
 <div class="transparent-image-component">
    <!-- Use an empty div with a background image -->
    <div class="background-image"></div>

    
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
  position: fixed;
  background-image: url('./assets/transparent-image.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-color: transparent;
  width: 50%; /* Adjust the width as needed */
  height: 50vh; /* Adjust the height as needed */
  opacity: 0.1; /* Adjust the opacity to control transparency */
  /* Add other styles as necessary */
}
</style>
