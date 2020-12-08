<template>
  <div class="banner">{{message}}
    <slot></slot>
   </div>

</template>

<script>
export default {
  name: "Banner"
}
</script>

<style scoped>
.banner {
  background-color: #f8f8f8;
}
</style>