<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
<div id="building">
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <HelloWorld/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0;
}

   html,body{
      margin:0;
      padding:0;
      
      width:100%;
   }

#building{
background:url("./assets/back.png");
width:100%;
height:100%;
/* position:fixed; */
background-size:100% 100%;
}
</style>
