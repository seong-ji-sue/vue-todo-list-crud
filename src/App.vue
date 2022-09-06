<template>
  <div class="layout-wrapper">
    <to-do-list />
  </div>
</template>

<script>
import ToDoList from "@/components/ToDoList";

export default {
  name: 'App',
  components: {
    ToDoList,
  }
}
</script>

<style>
.layout-wrapper{
  text-align: center;
}
</style>
