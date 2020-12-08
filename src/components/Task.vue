<template>
  <li>
    <span
        :class="{taskDone:taskToDisplay.isDone}"
        @click="endTask">
      {{taskToDisplay.name }}
    </span>

    <button @click="deleteTask">Supprimer</button>
  </li>
</template>

<script>
import{enMajuscule} from "@/utils";

export default {
name: "Task",
  props: {
    taskToDisplay: {
      type: Object,
      default: {
        id: Number,
        name: String,
        isDone: Boolean
      }
    },
  },
  methods: {
    deleteTask() {
      this.$emit("remove")
    },
    endTask() {
      this.$emit("done")
    }
  },
  filters: {
    enMajuscule
  }
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
