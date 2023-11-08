<template>
  <div>
    <Task
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      @delete-task="$emit('delete-task', task.id)"
      v-for="task in tasks"
      :key="task.id"
      :task="task"
    />
  </div>
</template>
  
  <script>
import Task from "./Task.vue";

export default {
  name: "Tasks",
  props: {
    tasks: {
      type: Array,
      required: true,
    },
  },
  components: {
    Task,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>