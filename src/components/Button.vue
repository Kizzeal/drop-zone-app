<template>
  <button
    @click="onClick()"
    :style="{ background: color, transition: 1 }"
    class="btn"
  >
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
  },
  methods: {
    onClick() {
      this.$emit("btn-click");
    },
  },
};
</script>

<style scoped>
/* .btn {
  transition: all 500ms ease-in-out;
} */
</style>
