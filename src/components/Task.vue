<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }}
      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
  // methods: {
  //   onDelete(id) {
  //     this.$emit("delete-task", id);
  //   },
  // },
};
</script>

<style scoped>
.fas {
  color: red;
}
.task {
  background: #212221;
  /* background: #c8d8e8; */
  border-radius: 5px;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}

.task.reminder {
  border-left: 5px solid #42b983;
}

.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
