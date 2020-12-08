<template>
  <div id="app">
    <Banner><b>Message du jour: </b>Salut à tous</Banner>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TodolistComponent from "@/components/TodolistComponent";
import TestComponent from "@/components/TestComponent";
import Banner from "@/components/Banner";

export default {
  name: 'App',
  components: {
    Banner,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
