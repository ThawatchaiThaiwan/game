<template>
  <div id="app">
    <img alt="logo game" src="./assets/logo1.png">
    <HelloWorld msg="Welcome to Game"/>
  </div>
 
  


</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: 'Abril Fatface', cursive;
  font-size:30px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color:red;
  margin-top: 60px;  
  background: url(https://cdnb.artstation.com/p/assets/images/images/014/281/887/original/brandon-ellis-cyber.gif?1543324220) no-repeat center fixed;
  background-size: cover;
    
    
}

</style>
