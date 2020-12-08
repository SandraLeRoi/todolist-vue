<template>
  <li>
    <span
        :class="{taskDone:taskToDisplay.isDone}"
        @click="$emit('end-task')">
      {{taskToDisplay.message}}
    </span>

    <button @click="deleteTask">Supprimer</button>
  </li>
</template>

<script>
export default {
name: "Task",
  props: {
    taskToDisplay: {
      type: Object,
      default: {
        message: "",
        isDone: false
      }
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
span{
  width: 50%;
  display: inline-block;
}
.taskDone {
  text-decoration: line-through;
  color: darkgrey;
}

</style>