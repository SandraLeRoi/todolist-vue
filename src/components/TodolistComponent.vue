<template>
  <div>
    <h1>{{ message }}</h1>

    <input type="text" v-model="newTask">
    <button @click="addTask">Ajouter une tache</button>

    <div :key="index" class="task" v-for="(task, index) in tasks">
      <h1>{{ task }}</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodolistComponent",
  data() {
    return {
      newTask: "",
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
      this.tasks.push(this.newTask)
    }
  },
}
</script>

<style scoped>

</style>