<template>
  <!-- The v-for directive basically helps loops and otuput something like the map function in react -->
  <!-- Just like in React we the key attribute when using map, here we have the :key attribute -->
  <div :key="task.id" v-for="task in tasks">
    <Task
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      @delete-task="$emit('delete-task', task.id)"
      :task="task"
    />
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>
