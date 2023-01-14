<template>
  <button @click="onClick()" :style="{ background: color }" class="btn">
    {{ text }}
  </button>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Button",
  props: {
    text: {
      type: String,
      default: " ",
    },
    color: String,
  },
  methods: {
    onClick() {
      console.log("btn click");
    },
  },
};
</script>
