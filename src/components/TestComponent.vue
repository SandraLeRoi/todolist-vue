<template>
  <div>
    <h1 v-if="name"> {{ name }}</h1>
    <h2 v-else>Hello</h2>
    <input type="text" v-model="name"/>
    <slot></slot>
  </div>
</template>

<script>
import TodolistComponent from "@/components/TodolistComponent";
export default {
name: "TestComponent",
  data() {
    return {
      name: ""
    }
  },
}
</script>

<style scoped>


</style>