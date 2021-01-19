<template>
  <li class="task-item" :priority="priority">
    <label>
      <input type="checkbox">
    </label>
    <p>{{title}}</p>
  </li>
</template>

<script>
export default {
  name: "TaskItem",
  props: {
    title: {
      type: String
    },
    priority:{
      type: String
    }
  }
}
</script>

<style scoped>

</style>