<template>
  <div>
    <h1>{{ message }}</h1>

    <input ref="myInput" type="text" v-model="currentTask" @keypress.enter="addTask">
    <button @click="addTask">Ajouter une tache</button>

    <ul>
      <Task
          :key=i
          v-for="(task, i) in tasks"
          :taskToDisplay="task"
          @remove="removeTask(i)"
          @end-task="task.isDone = true"
      />
    </ul>
  </div>
</template>

<script>
import Task from "@/components/Task";

export default {
  name: "TodolistComponent",
  components: {Task},
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
      this.tasks.push({
        message: this.currentTask,
        isDone: false
      })
      this.currentTask = ""
      this.$refs.myInput.focus()
    },
    removeTask(index){
      this.tasks.splice(index,1)
    }
  },
}
</script>

<style scoped>

</style>