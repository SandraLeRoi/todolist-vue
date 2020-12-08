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
          @remove="removeTask(i, task.id)"
          @done="taskDone(task)"
      />
    </ul>
  </div>
</template>

<script>
import Task from "@/components/Task";
import Axios from "axios";

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
    async addTask() {
      Axios.post("https://todo-hoc.dunarr.com/tasks/5fcf7991ae75c", ({
        name: this.currentTask,
        isDone:false
      }))
      this.tasks.push(response.data)
      this.currentTask = ""
      this.$refs.myInput.focus()
    },
    removeTask(index, id){
      Axios.delete("https://todo-hoc.dunarr.com/tasks/5fcf7991ae75c/" + id)
      this.tasks.splice(index,1)

    },
    async fetchTasks() {
      const response = await Axios.get("https://todo-hoc.dunarr.com/tasks/5fcf7991ae75c")
      this.tasks = response.data.tasks
    },
    taskDone(task){
      const done = !task.isDone
      Axios.put("https://todo-hoc.dunarr.com/tasks/5fcf7991ae75c/" + task.id,{
        isDone: done
      } )
      task.isDone = done
    }
  },
  mounted() {
    this.fetchTasks()
  }
}
</script>

<style scoped>

</style>
