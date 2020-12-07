<template>
  <div>
    <h1>{{ message }}</h1>

    <input type="text" v-model="currentTask" @keypress.enter="addTask">
    <button @click="addTask">Ajouter une tache</button>

    <div :key="index" class="task" v-for="(task, index) in tasks">
      <li>{{ task }}</li>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodolistComponent",
  data() {
    return {
      currentTask: "",
      tasks: []
    }
  },
  props: {
    message: {
      type: String,
      default: "Liste de tâches"
    },
  },
  methods: {
    addTask() {
      this.tasks.push(this.currentTask),
      this.currentTask = ""
    }
  },
}
</script>

<style scoped>

</style>