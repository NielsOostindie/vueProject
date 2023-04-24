<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }}
      <div class="icon-container">
      <i @click="$emit('task-info', task.id)" class="fa-solid fa-chevron-down"></i>
      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </div>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  }
};
</script>

<style scoped>
*{
    z-index: 1;
}

.fas {
  color: red;
}

.icon-container i {
  padding-left: 15%;
}

.icon-container{
width: 14%;
}

.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
