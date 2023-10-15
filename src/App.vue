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
  position: center;
  background-image: url('./assets/transparent-image.png');
  background-size: contain;
  background-repeat: no-repeat;
  background-color: transparent;
  width: 60%;
  height: 100vh; 
  opacity: 0.1; 
  margin: auto;

  
}
</style>
