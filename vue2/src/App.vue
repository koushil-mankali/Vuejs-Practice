<script lang="ts">
  import Home from './components/Home.vue'

  export default {
    components: {
      Home,
    },
    data(){
      return {
        nameOne: "One",
        nameTwo: "Two",
      }
    },
  }
</script>

<template>
  <Home :name="nameOne" :num="444" :isMainPage="true" />
  <Home :name="nameTwo" :num="444" :isMainPage="true" />
  <Home id="home" name="Three" :num="444" :isMainPage="true" />
</template>

<style> 
  body{
    height: 100vh;
    background-color: #42B883;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>