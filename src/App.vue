<template>
  <div id="app">
    <!-- <button @click="fetchFilm">Cliquez moi</button>
    {{film}}-->
    <TodolistComponent/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TodolistComponent from "@/components/TodolistComponent";
import TestComponent from "@/components/TestComponent";
import Banner from "@/components/Banner";
import Axios from "axios";

export default {
  name: 'App',
  components: {
    Banner,
    TodolistComponent,
    TestComponent,
    HelloWorld,
  },
  data() {
    return {
      film: null
    }
  },
  methods: {
    async fetchFilm() {
      const response = await Axios.get("https://swapi.dev/api/films/1")
      this.film = response.data
    }
  },
  mounted() {
    this.fetchFilm()
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
