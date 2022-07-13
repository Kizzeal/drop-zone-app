<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      class="effect"
      @btn-click="$emit('toggle-add-task')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? '#df211a9f' : '#42b9839f'"
    />
  </header>
</template>

<script>
import Button from "./Button";

export default {
  name: "FirstPage",
  props: {
    title: {
      type: String,
    },
    showAddTask: {
      type: Boolean,
    },
  },
  components: {
    Button,
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
}
/* .effect {
  transition: all 500ms ease-in-out;
} */
</style>
