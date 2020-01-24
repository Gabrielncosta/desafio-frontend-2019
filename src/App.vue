<template>
  <div id="app">
    <!--   <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
    <router-view/>
  </div>
</template>

<script>
import Dinero from 'dinero.js'
export default {
  
}
</script>
<style>
@font-face {
  font-family: "SourceSansPro-Bold";
  src: url("./assets/fonts/SourceSansPro-Black.ttf") format("truetype");
}

@font-face {
  font-family: "SourceSansPro-Black";
  src: url("./assets/fonts/SourceSansPro-Bold.ttf") format("truetype");
}

@font-face {
  font-family: "SourceSansPro-Regular";
  src: url("./assets/fonts/SourceSansPro-Regular.ttf") format("truetype");
}


#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

</style>
