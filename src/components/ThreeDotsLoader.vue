<template>
  <v-btn flat>
    three dots hover
    <v-dialog v-model="dialog" activator="parent">
      <v-card>
        <div class="loader">
          <span class="loader__element"></span>
          <span class="loader__element"></span>
          <span class="loader__element"></span>
        </div>
        <v-card-actions>
          <v-btn color="primary" block @click="dialog = false">Close</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-btn>
</template>

<script setup lang="ts">
import { ref } from "vue";

const dialog = ref(false);
</script>

<style scoped>
.loader {
  background-color: #ecf0f1;
  overflow: hidden;
  width: 100%;
  height: 100%;
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  align-items: center;
  align-content: center;
  justify-content: center;
  z-index: 100000;
}

.loader__element {
  border-radius: 100%;
  border: 5px solid #555;
  margin: calc(5px * 2);
}

.loader__element:nth-child(1) {
  animation: preloader 0.6s ease-in-out alternate infinite;
}

.loader__element:nth-child(2) {
  animation: preloader 0.6s ease-in-out alternate 0.2s infinite;
}

.loader__element:nth-child(3) {
  animation: preloader 0.6s ease-in-out alternate 0.4s infinite;
}

@keyframes preloader {
  100% {
    transform: scale(2);
  }
}
</style>
