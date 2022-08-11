<template>
  <div class="home">
    <h1>DropZone</h1>
    <DropZone @drop.prevent="drop" @change="selectedFile" />
    <span class="file-info"> File: {{ dropzoneFile.name }} </span>
  </div>
</template>

<script setup>
import DropZone from "@/components/DropZone.vue";
import { ref } from "vue";

const dropzoneFile = ref("");

const drop = (e) => {
  dropzoneFile.value = e.dataTransfer.files[0];
};

const selectedFile = () => {
  dropzoneFile.value = document.querySelector(".dropzoneFile").files[0];
};
</script>

<style scoped>
.home {
  height: 100vh;
  display: grid;
  place-content: center;
}
h1 {
  font-size: 2.5em;
  margin-bottom: 1em;
}

.file-info {
  margin-top: 2em;
}
</style>
