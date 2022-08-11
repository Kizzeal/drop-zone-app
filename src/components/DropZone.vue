<template>
  <div
    @dragenter.prevent="toggleActive"
    @dragleave.prevent="toggleActive"
    @dragover.prevent=""
    @drop.prevent="toggleActive"
    :class="{ 'active-dropzone': active }"
    class="dropzone"
  >
    <span>Drag or Drop File</span>
    <span>OR</span>
    <label for="dropzoneFile">Select File</label>
    <input type="file" name="" id="dropzoneFile" class="dropzoneFile" />
  </div>
</template>

<script setup>
import { ref } from "vue";

const active = ref(false);

const toggleActive = () => {
  active.value = !active.value;
};
</script>

<style scoped>
.dropzone {
  width: 25em;
  height: 12.5em;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  /* display: grid;
  place-items: center; */
  row-gap: 1em;
  border: 2px dashed #41b883;
  background: hsla(240, 29%, 10%, 0.5);
  transition: all 0.5s ease;
}

.dropzone label {
  padding: 0.5em 0.75em;
  color: #fff;
  background-color: #41b883;
  transition: all 0.5s ease;
}

.dropzone input {
  display: none;
}

.active-dropzone {
  color: #fff;
  border-color: hsla(240, 29%, 10%, 0.5);
  background-color: #41b883;
}

.active-dropzone label {
  background-color: #fff;
  color: #41b883;
}
</style>
