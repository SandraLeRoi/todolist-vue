<template>
  <li>
    {{taskToDisplay}}
    <button @click="deleteTask">Supprimer</button>
  </li>
</template>

<script>
export default {
name: "Task",
  props: {
    taskToDisplay: {
      type: String,
      default: ""
    },
  },
  methods: {
    deleteTask() {
      this.$emit("remove")
    }
  },
}
</script>

<style scoped>

</style>