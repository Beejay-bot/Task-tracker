<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePage"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? 'red' : 'green'"
      @btn-click="$emit('toggle-add-task')"
    />
  </header>
</template>

<!-- This right here is to export the component. (something similar to exporting React components also) -->
<script>
import Button from "./Button.vue";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Header", // The header here is the name given to this component. It can be any name depending on the components functionality.
  //passing props into components. (Same props as used in React.) The props properties can be defined in arrays or an object.
  props: {
    title: {
      type: String, // state the type or expected datatype that is meant to be passed to this component.
      default: "Hello, this is an header component", // the default data of this props if nothing is not passed.
    },
    showAddTask: Boolean,
  },
  components: {
    Button,
  },
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>

<!-- The scoped attribute here means this styling is only for this component -->
<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
